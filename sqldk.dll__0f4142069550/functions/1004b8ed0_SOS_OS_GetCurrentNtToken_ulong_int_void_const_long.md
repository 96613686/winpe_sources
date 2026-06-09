# SOS_OS::GetCurrentNtToken(ulong,int,void * * const,long *)

- ea: `0x1004b8ed0`
- end: `0x1004b8f5f`
- name: `?GetCurrentNtToken@SOS_OS@@SA?AW4SOS_RESULT@@KHQEAPEAXPEAJ@Z`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1004b8ed0`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1004b8ef6`
- `KERNEL32!GetCurrentThread` at `0x1004b8ef6`
- `KERNEL32!GetLastError` at `0x1004b8f11`
- `KERNEL32!GetLastError` at `0x1004b8f11`
- `ADVAPI32!OpenThreadToken` at `0x1004b8f07`
- `ADVAPI32!OpenThreadToken` at `0x1004b8f07`

## pseudocode

```c
__int64 __fastcall SOS_OS::GetCurrentNtToken(DWORD a1, BOOL a2, void **a3, unsigned int *a4)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v10; // ecx

  *a3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, a1, a2, a3) )
    return 0;
  LastError = GetLastError();
  v10 = LastError > 0 ? (unsigned __int16)LastError | 0x80070000 : LastError;
  *a4 = v10;
  *a3 = 0;
  if ( LastError == 1008 || LastError == 1309 )
    return 0;
  else
    return 0x80000000LL;
}

```

## disassembly

```asm
0x1004b8ed0  mov     [rsp+arg_0], rbx
0x1004b8ed5  mov     [rsp+arg_8], rsi
0x1004b8eda  mov     [rsp+arg_10], rdi
0x1004b8edf  push    r14
0x1004b8ee1  sub     rsp, 20h
0x1004b8ee5  mov     r14, r9
0x1004b8ee8  mov     qword ptr [r8], 0
0x1004b8eef  mov     rsi, r8
0x1004b8ef2  mov     ebx, edx
0x1004b8ef4  mov     edi, ecx
0x1004b8ef6  call    cs:__imp_GetCurrentThread
0x1004b8efc  mov     r9, rsi; TokenHandle
0x1004b8eff  mov     r8d, ebx; OpenAsSelf
0x1004b8f02  mov     rcx, rax; ThreadHandle
0x1004b8f05  mov     edx, edi; DesiredAccess
0x1004b8f07  call    cs:__imp_OpenThreadToken
0x1004b8f0d  test    eax, eax
0x1004b8f0f  jnz     short loc_1004B8F47
0x1004b8f11  call    cs:__imp_GetLastError
0x1004b8f17  test    eax, eax
0x1004b8f19  jg      short loc_1004B8F1F
0x1004b8f1b  mov     ecx, eax
0x1004b8f1d  jmp     short loc_1004B8F28
0x1004b8f1f  movzx   ecx, ax
0x1004b8f22  or      ecx, 80070000h
0x1004b8f28  mov     [r14], ecx
0x1004b8f2b  mov     qword ptr [rsi], 0
0x1004b8f32  cmp     eax, 3F0h
0x1004b8f37  jz      short loc_1004B8F47
0x1004b8f39  cmp     eax, 51Dh
0x1004b8f3e  jz      short loc_1004B8F47
0x1004b8f40  mov     eax, 80000000h
0x1004b8f45  jmp     short loc_1004B8F49
0x1004b8f47  xor     eax, eax
0x1004b8f49  mov     rbx, [rsp+28h+arg_0]
0x1004b8f4e  mov     rsi, [rsp+28h+arg_8]
0x1004b8f53  mov     rdi, [rsp+28h+arg_10]
0x1004b8f58  add     rsp, 20h
0x1004b8f5c  pop     r14
0x1004b8f5e  retn
```
