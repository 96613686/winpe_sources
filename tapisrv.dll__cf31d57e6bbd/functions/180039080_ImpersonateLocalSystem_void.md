# ImpersonateLocalSystem(void)

- ea: `0x180039080`
- end: `0x1800390de`
- name: `?ImpersonateLocalSystem@@YAJXZ`
- size: `94`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180037344`
- `0x18003a9ec`
- `0x18003bcc8`

## callees

- `0x1800384f4`
- `0x180039080`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800390d0`
- `KERNEL32!CloseHandle` at `0x1800390d0`
- `KERNEL32!GetLastError` at `0x1800390ae`
- `KERNEL32!GetLastError` at `0x1800390ae`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1800390a4`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1800390a4`

## pseudocode

```c
__int64 __fastcall ImpersonateLocalSystem(__int64 a1, int a2)
{
  int LocalSystemToken; // ebx
  signed int LastError; // eax
  HANDLE hToken; // [rsp+30h] [rbp+8h] BYREF

  hToken = 0;
  LocalSystemToken = GetLocalSystemToken(&hToken, a2);
  if ( LocalSystemToken >= 0 && !ImpersonateLoggedOnUser(hToken) )
  {
    LastError = GetLastError();
    LocalSystemToken = LastError;
    if ( LastError > 0 )
      LocalSystemToken = (unsigned __int16)LastError | 0x80070000;
  }
  if ( hToken )
    CloseHandle(hToken);
  return (unsigned int)LocalSystemToken;
}

```

## disassembly

```asm
0x180039080  push    rbx
0x180039082  sub     rsp, 20h
0x180039086  lea     rcx, [rsp+28h+hToken]; void **
0x18003908b  mov     [rsp+28h+hToken], 0
0x180039094  call    ?GetLocalSystemToken@@YAJPEAPEAX@Z; GetLocalSystemToken(void * *)
0x180039099  mov     ebx, eax
0x18003909b  test    eax, eax
0x18003909d  js      short loc_1800390C3
0x18003909f  mov     rcx, [rsp+28h+hToken]; hToken
0x1800390a4  call    cs:__imp_ImpersonateLoggedOnUser
0x1800390aa  test    eax, eax
0x1800390ac  jnz     short loc_1800390C3
0x1800390ae  call    cs:__imp_GetLastError
0x1800390b4  mov     ebx, eax
0x1800390b6  test    eax, eax
0x1800390b8  jle     short loc_1800390C3
0x1800390ba  movzx   ebx, ax
0x1800390bd  or      ebx, 80070000h
0x1800390c3  cmp     [rsp+28h+hToken], 0
0x1800390c9  jz      short loc_1800390D6
0x1800390cb  mov     rcx, [rsp+28h+hToken]; hObject
0x1800390d0  call    cs:__imp_CloseHandle
0x1800390d6  mov     eax, ebx
0x1800390d8  add     rsp, 20h
0x1800390dc  pop     rbx
0x1800390dd  retn
```
