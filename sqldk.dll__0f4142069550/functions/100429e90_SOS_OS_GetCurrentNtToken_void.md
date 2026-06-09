# SOS_OS::GetCurrentNtToken(void * *)

- ea: `0x100429e90`
- end: `0x100429ecb`
- name: `?GetCurrentNtToken@SOS_OS@@SA?AW4SOS_RESULT@@PEAPEAX@Z`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x100429e90`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x100429ea0`
- `KERNEL32!GetCurrentThread` at `0x100429ea0`
- `KERNEL32!GetLastError` at `0x1004b3dd6`
- `KERNEL32!GetLastError` at `0x1004b3dd6`
- `ADVAPI32!OpenThreadToken` at `0x100429eb5`
- `ADVAPI32!OpenThreadToken` at `0x100429eb5`

## pseudocode

```c
__int64 __fastcall SOS_OS::GetCurrentNtToken(void **a1)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax

  *a1 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, a1) )
    return 0;
  LastError = GetLastError();
  *a1 = 0;
  if ( LastError == 1008 || LastError == 1309 )
    return 0;
  else
    return 0x80000000LL;
}

```

## disassembly

```asm
0x100429e90  push    rbx
0x100429e92  sub     rsp, 20h
0x100429e96  mov     rbx, rcx
0x100429e99  mov     qword ptr [rcx], 0
0x100429ea0  call    cs:__imp_GetCurrentThread
0x100429ea6  mov     edx, 0Ch; DesiredAccess
0x100429eab  mov     r9, rbx; TokenHandle
0x100429eae  mov     rcx, rax; ThreadHandle
0x100429eb1  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x100429eb5  call    cs:__imp_OpenThreadToken
0x100429ebb  test    eax, eax
0x100429ebd  jz      loc_1004B3DD6
0x100429ec3  xor     eax, eax
0x100429ec5  add     rsp, 20h
0x100429ec9  pop     rbx
0x100429eca  retn
0x1004b3dd6  call    cs:__imp_GetLastError
0x1004b3ddc  mov     qword ptr [rbx], 0
0x1004b3de3  cmp     eax, 3F0h
0x1004b3de8  jz      loc_100429EC3
0x1004b3dee  cmp     eax, 51Dh
0x1004b3df3  jz      loc_100429EC3
0x1004b3df9  mov     eax, 80000000h
0x1004b3dfe  add     rsp, 20h
0x1004b3e02  pop     rbx
0x1004b3e03  retn
```
