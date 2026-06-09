# VelocityPollerStartup(void)

- ea: `0x18003444c`
- end: `0x18003450c`
- name: `?VelocityPollerStartup@@YAXXZ`
- size: `192`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001d2f0`

## callees

- `0x180023be0`
- `0x18003444c`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800344a7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800344a7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800344d8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800344d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800344f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800344f1`

## pseudocode

```c
void VelocityPollerStartup(void)
{
  int v0; // edi
  unsigned int i; // ebx

  if ( !hObject )
  {
    v0 = 0;
    for ( i = 0; i < 2; ++i )
    {
      if ( ((unsigned int (*)(void))*(&funcs_18003447E + 6 * (int)i))() )
      {
        *((_BYTE *)&funcs_180034546 + 48 * (int)i + 40) = 1;
        v0 = 1;
      }
    }
    if ( v0 )
    {
      hHandle = CreateEventW(0, 0, 0, 0);
      if ( hHandle )
      {
        hObject = CreateThread(0, 0, VelocityPollerThreadProc, 0, 0, 0);
        if ( !hObject )
        {
          CloseHandle(hHandle);
          hHandle = 0;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18003444c  push    rbx
0x18003444e  push    rsi
0x18003444f  push    rdi
0x180034450  push    r14
0x180034452  sub     rsp, 38h
0x180034456  cmp     cs:hObject, 0
0x18003445e  jnz     loc_180034502
0x180034464  xor     edi, edi
0x180034466  lea     r14, funcs_180034546
0x18003446d  xor     ebx, ebx
0x18003446f  movsxd  rax, ebx
0x180034472  lea     rsi, [rax+rax*2]
0x180034476  add     rsi, rsi
0x180034479  mov     rax, (funcs_18003447E - 180053010h)[r14+rsi*8]
0x18003447e  call    _guard_dispatch_icall$thunk$10345483385596137414; WARBIRD_DELAY_LOAD::SetBkMode(HDC__ *,int) ...
0x180034483  test    eax, eax
0x180034485  jz      short loc_180034492
0x180034487  mov     byte ptr [r14+rsi*8+28h], 1
0x18003448d  mov     edi, 1
0x180034492  inc     ebx
0x180034494  cmp     ebx, 2
0x180034497  jb      short loc_18003446F
0x180034499  test    edi, edi
0x18003449b  jz      short loc_180034502
0x18003449d  xor     r9d, r9d; lpName
0x1800344a0  xor     r8d, r8d; bInitialState
0x1800344a3  xor     edx, edx; bManualReset
0x1800344a5  xor     ecx, ecx; lpEventAttributes
0x1800344a7  call    cs:__imp_CreateEventW
0x1800344ad  mov     cs:hHandle, rax
0x1800344b4  test    rax, rax
0x1800344b7  jz      short loc_180034502
0x1800344b9  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x1800344c2  lea     r8, VelocityPollerThreadProc; lpStartAddress
0x1800344c9  xor     r9d, r9d; lpParameter
0x1800344cc  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x1800344d4  xor     edx, edx; dwStackSize
0x1800344d6  xor     ecx, ecx; lpThreadAttributes
0x1800344d8  call    cs:__imp_CreateThread
0x1800344de  mov     cs:hObject, rax
0x1800344e5  test    rax, rax
0x1800344e8  jnz     short loc_180034502
0x1800344ea  mov     rcx, cs:hHandle; hObject
0x1800344f1  call    cs:__imp_CloseHandle
0x1800344f7  mov     cs:hHandle, 0
0x180034502  add     rsp, 38h
0x180034506  pop     r14
0x180034508  pop     rdi
0x180034509  pop     rsi
0x18003450a  pop     rbx
0x18003450b  retn
```
