# CaptureThreadToken(void * *,int)

- ea: `0x1800729f8`
- end: `0x180072a9d`
- name: `?CaptureThreadToken@@YAJPEAPEAXH@Z`
- size: `165`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180029d80`
- `0x18002a758`
- `0x18002b210`
- `0x18007200c`

## callees

- `0x1800283bc`
- `0x1800729f8`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x180072a20`
- `ntdll!NtOpenThreadToken` at `0x180072a20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072a07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072a07`

## pseudocode

```c
__int64 __fastcall CaptureThreadToken(__int64 *TokenHandle, int a2)
{
  HANDLE CurrentThread; // rax
  NTSTATUS v5; // eax
  __int64 v6; // rax
  unsigned int v7; // ebx
  _DWORD v9[10]; // [rsp+30h] [rbp-28h] BYREF

  CurrentThread = GetCurrentThread();
  v5 = NtOpenThreadToken(CurrentThread, a2 != 0 ? 14 : 12, 1u, (PHANDLE)TokenHandle);
  if ( v5 != -1073741700 )
  {
    switch ( v5 )
    {
      case -1073741790:
        v7 = 5;
        break;
      case -1073741658:
        v6 = 4294967294LL;
        goto LABEL_3;
      case 0:
        return 0;
      default:
        v7 = 14;
        break;
    }
    *TokenHandle = 0;
    v9[2] = v5;
    v9[0] = 3;
    RpcpErrorAddRecord(2u, v7, 0x460u, 1, (struct tagParam *)v9);
    return v7;
  }
  v6 = 4294967293LL;
LABEL_3:
  *TokenHandle = v6;
  return 0;
}

```

## disassembly

```asm
0x1800729f8  mov     [rsp+arg_0], rbx
0x1800729fd  push    rdi
0x1800729fe  sub     rsp, 50h
0x180072a02  mov     ebx, edx
0x180072a04  mov     rdi, rcx
0x180072a07  call    cs:__imp_GetCurrentThread
0x180072a0d  neg     ebx
0x180072a0f  mov     r9, rdi; TokenHandle
0x180072a12  mov     r8b, 1; OpenAsSelf
0x180072a15  mov     rcx, rax; ThreadHandle
0x180072a18  sbb     edx, edx
0x180072a1a  and     edx, 2
0x180072a1d  add     edx, 0Ch; DesiredAccess
0x180072a20  call    cs:__imp_NtOpenThreadToken
0x180072a26  xor     ecx, ecx
0x180072a28  cmp     eax, 0C000007Ch
0x180072a2d  jnz     short loc_180072A46
0x180072a2f  mov     eax, 0FFFFFFFDh
0x180072a34  mov     [rdi], rax
0x180072a37  mov     ebx, ecx
0x180072a39  mov     eax, ebx
0x180072a3b  mov     rbx, [rsp+58h+arg_0]
0x180072a40  add     rsp, 50h
0x180072a44  pop     rdi
0x180072a45  retn
0x180072a46  cmp     eax, 0C0000022h
0x180072a4b  jz      short loc_180072A66
0x180072a4d  cmp     eax, 0C00000A6h
0x180072a52  jz      short loc_180072A5F
0x180072a54  test    eax, eax
0x180072a56  jz      short loc_180072A37
0x180072a58  mov     ebx, 0Eh
0x180072a5d  jmp     short loc_180072A6B
0x180072a5f  mov     eax, 0FFFFFFFEh
0x180072a64  jmp     short loc_180072A34
0x180072a66  mov     ebx, 5
0x180072a6b  mov     [rdi], rcx
0x180072a6e  mov     r9d, 1; int
0x180072a74  mov     [rsp+58h+var_20], eax
0x180072a78  mov     r8d, 460h; unsigned __int16
0x180072a7e  lea     rax, [rsp+58h+var_28]
0x180072a83  mov     [rsp+58h+var_28], 3
0x180072a8b  mov     edx, ebx; int
0x180072a8d  mov     [rsp+58h+var_38], rax; struct tagParam *
0x180072a92  lea     ecx, [r9+1]; unsigned int
0x180072a96  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180072a9b  jmp     short loc_180072A39
```
