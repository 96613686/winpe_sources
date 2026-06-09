# RestoreAndCloseThreadToken

- ea: `0x18001bd40`
- end: `0x18001bda3`
- name: `RestoreAndCloseThreadToken`
- size: `99`
- prototype: `void __fastcall(HANDLE hObject)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001bd40`
- `0x18001c708`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bd7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bd7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bd97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bd97`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001bd52`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001bd52`

## pseudocode

```c
void __fastcall RestoreAndCloseThreadToken(HANDLE hObject)
{
  DWORD LastError; // eax
  __int64 v3; // rdx
  __int64 v4; // r8

  if ( hObject )
  {
    if ( !SetThreadToken(0, hObject)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v3, v4, LastError);
    }
    CloseHandle(hObject);
  }
}

```

## disassembly

```asm
0x18001bd40  test    rcx, rcx
0x18001bd43  jz      short locret_18001BDA2
0x18001bd45  push    rbx
0x18001bd46  sub     rsp, 20h
0x18001bd4a  mov     rbx, rcx
0x18001bd4d  mov     rdx, rcx; Token
0x18001bd50  xor     ecx, ecx; Thread
0x18001bd52  call    cs:__imp_SetThreadToken
0x18001bd58  test    eax, eax
0x18001bd5a  jnz     short loc_18001BD94
0x18001bd5c  mov     rax, cs:WPP_GLOBAL_Control
0x18001bd63  lea     rcx, WPP_GLOBAL_Control
0x18001bd6a  cmp     rax, rcx
0x18001bd6d  jz      short loc_18001BD94
0x18001bd6f  test    byte ptr [rax+1Ch], 40h
0x18001bd73  jz      short loc_18001BD94
0x18001bd75  cmp     byte ptr [rax+19h], 2
0x18001bd79  jb      short loc_18001BD94
0x18001bd7b  call    cs:__imp_GetLastError
0x18001bd81  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd88  mov     r9d, eax
0x18001bd8b  mov     rcx, [rcx+10h]
0x18001bd8f  call    WPP_SF_d
0x18001bd94  mov     rcx, rbx; hObject
0x18001bd97  call    cs:__imp_CloseHandle
0x18001bd9d  add     rsp, 20h
0x18001bda1  pop     rbx
0x18001bda2  retn
```
