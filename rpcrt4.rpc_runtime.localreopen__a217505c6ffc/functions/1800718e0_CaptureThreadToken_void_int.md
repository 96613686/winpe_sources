# CaptureThreadToken(void * *,int)

- ea: `0x1800718e0`
- end: `0x180071992`
- name: `?CaptureThreadToken@@YAJPEAPEAXH@Z`
- size: `178`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002b04c`
- `0x18002b9fc`
- `0x18002c4f0`
- `0x180070fec`

## callees

- `0x1800295d8`
- `0x1800718e0`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x18007190e`
- `ntdll!NtOpenThreadToken` at `0x18007190e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800718ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800718ef`

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
0x1800718e0  mov     [rsp+arg_0], rbx
0x1800718e5  push    rdi
0x1800718e6  sub     rsp, 50h
0x1800718ea  mov     ebx, edx
0x1800718ec  mov     rdi, rcx
0x1800718ef  call    cs:__imp_GetCurrentThread
0x1800718f6  nop     dword ptr [rax+rax+00h]
0x1800718fb  neg     ebx
0x1800718fd  mov     r9, rdi; TokenHandle
0x180071900  mov     r8b, 1; OpenAsSelf
0x180071903  mov     rcx, rax; ThreadHandle
0x180071906  sbb     edx, edx
0x180071908  and     edx, 2
0x18007190b  add     edx, 0Ch; DesiredAccess
0x18007190e  call    cs:__imp_NtOpenThreadToken
0x180071915  nop     dword ptr [rax+rax+00h]
0x18007191a  xor     ecx, ecx
0x18007191c  cmp     eax, 0C000007Ch
0x180071921  jnz     short loc_18007193B
0x180071923  mov     eax, 0FFFFFFFDh
0x180071928  mov     [rdi], rax
0x18007192b  mov     ebx, ecx
0x18007192d  mov     eax, ebx
0x18007192f  mov     rbx, [rsp+58h+arg_0]
0x180071934  add     rsp, 50h
0x180071938  pop     rdi
0x180071939  retn
0x18007193b  cmp     eax, 0C0000022h
0x180071940  jz      short loc_18007195B
0x180071942  cmp     eax, 0C00000A6h
0x180071947  jz      short loc_180071954
0x180071949  test    eax, eax
0x18007194b  jz      short loc_18007192B
0x18007194d  mov     ebx, 0Eh
0x180071952  jmp     short loc_180071960
0x180071954  mov     eax, 0FFFFFFFEh
0x180071959  jmp     short loc_180071928
0x18007195b  mov     ebx, 5
0x180071960  mov     [rdi], rcx
0x180071963  mov     r9d, 1; int
0x180071969  mov     [rsp+58h+var_20], eax
0x18007196d  mov     r8d, 460h; unsigned __int16
0x180071973  lea     rax, [rsp+58h+var_28]
0x180071978  mov     [rsp+58h+var_28], 3
0x180071980  mov     edx, ebx; int
0x180071982  mov     [rsp+58h+var_38], rax; struct tagParam *
0x180071987  lea     ecx, [r9+1]; unsigned int
0x18007198b  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180071990  jmp     short loc_18007192D
```
