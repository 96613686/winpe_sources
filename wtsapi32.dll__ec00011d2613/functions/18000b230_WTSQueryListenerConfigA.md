# WTSQueryListenerConfigA

- ea: `0x18000b230`
- end: `0x18000b322`
- name: `WTSQueryListenerConfigA`
- size: `242`
- prototype: `BOOL __stdcall(HANDLE hServer, PVOID pReserved, DWORD Reserved, LPSTR pListenerName, PWTSLISTENERCONFIGA pBuffer)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800057f0`
- `0x180008acc`
- `0x18000a30c`
- `0x18000b230`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b288`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b2e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b311`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b288`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b2e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b311`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b2fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b309`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b2fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b309`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b29f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b29f`

## pseudocode

```c
BOOL __stdcall WTSQueryListenerConfigA(
        HANDLE hServer,
        PVOID pReserved,
        DWORD Reserved,
        LPSTR pListenerName,
        PWTSLISTENERCONFIGA pBuffer)
{
  LPWSTR v5; // rbx
  BOOL v6; // ebp
  struct _WTSLISTENERCONFIGW *v7; // rdi
  PWTSLISTENERCONFIGA v8; // rsi
  struct _WTSLISTENERCONFIGW *v9; // rax
  DWORD LastError; // esi
  LPWSTR pListenerNamea; // [rsp+60h] [rbp+8h] BYREF

  v5 = 0;
  v6 = 0;
  v7 = 0;
  pListenerNamea = 0;
  if ( hServer || pReserved || Reserved || !pListenerName || (v8 = pBuffer) == 0 )
  {
LABEL_12:
    SetLastError(0x57u);
    goto LABEL_13;
  }
  if ( !(unsigned int)CopyStringA((__int64)pListenerName, &pListenerNamea, 0) )
  {
    SetLastError(0x57u);
    v5 = pListenerNamea;
    goto LABEL_13;
  }
  v9 = (struct _WTSLISTENERCONFIGW *)LocalAlloc(0x40u, 0x544u);
  v5 = pListenerNamea;
  v7 = v9;
  if ( v9 && WTSQueryListenerConfigW(0, 0, 0, pListenerNamea, v9) )
  {
    if ( (unsigned int)ConvertListenerConfigFromUnicodeToAnsi(v7, v8) )
    {
      v6 = 1;
      goto LABEL_13;
    }
    goto LABEL_12;
  }
LABEL_13:
  LastError = GetLastError();
  if ( v5 )
    LocalFree(v5);
  if ( v7 )
    LocalFree(v7);
  SetLastError(LastError);
  return v6;
}

```

## disassembly

```asm
0x18000b230  push    rbx
0x18000b232  push    rbp
0x18000b233  push    rsi
0x18000b234  push    rdi
0x18000b235  sub     rsp, 38h
0x18000b239  xor     ebx, ebx
0x18000b23b  xor     ebp, ebp
0x18000b23d  xor     edi, edi
0x18000b23f  mov     [rsp+58h+pListenerName], rbx
0x18000b244  test    rcx, rcx
0x18000b247  jnz     loc_18000B2E0
0x18000b24d  test    rdx, rdx
0x18000b250  jnz     loc_18000B2E0
0x18000b256  test    r8d, r8d
0x18000b259  jnz     loc_18000B2E0
0x18000b25f  test    r9, r9
0x18000b262  jz      short loc_18000B2E0
0x18000b264  mov     rsi, [rsp+58h+pBuffer]
0x18000b26c  test    rsi, rsi
0x18000b26f  jz      short loc_18000B2E0
0x18000b271  xor     r8d, r8d
0x18000b274  lea     rdx, [rsp+58h+pListenerName]
0x18000b279  mov     rcx, r9
0x18000b27c  call    _CopyStringA
0x18000b281  test    eax, eax
0x18000b283  jnz     short loc_18000B295
0x18000b285  lea     ecx, [rbp+57h]; dwErrCode
0x18000b288  call    cs:__imp_SetLastError
0x18000b28e  mov     rbx, [rsp+58h+pListenerName]
0x18000b293  jmp     short loc_18000B2EB
0x18000b295  mov     edx, 544h; uBytes
0x18000b29a  mov     ecx, 40h ; '@'; uFlags
0x18000b29f  call    cs:__imp_LocalAlloc
0x18000b2a5  mov     rbx, [rsp+58h+pListenerName]
0x18000b2aa  mov     rdi, rax
0x18000b2ad  test    rax, rax
0x18000b2b0  jz      short loc_18000B2EB
0x18000b2b2  mov     r9, rbx; pListenerName
0x18000b2b5  mov     [rsp+58h+var_38], rax; pBuffer
0x18000b2ba  xor     r8d, r8d; Reserved
0x18000b2bd  xor     edx, edx; pReserved
0x18000b2bf  xor     ecx, ecx; hServer
0x18000b2c1  call    WTSQueryListenerConfigW
0x18000b2c6  test    eax, eax
0x18000b2c8  jz      short loc_18000B2EB
0x18000b2ca  mov     rdx, rsi
0x18000b2cd  mov     rcx, rdi
0x18000b2d0  call    ConvertListenerConfigFromUnicodeToAnsi
0x18000b2d5  test    eax, eax
0x18000b2d7  jz      short loc_18000B2E0
0x18000b2d9  mov     ebp, 1
0x18000b2de  jmp     short loc_18000B2EB
0x18000b2e0  mov     ecx, 57h ; 'W'; dwErrCode
0x18000b2e5  call    cs:__imp_SetLastError
0x18000b2eb  call    cs:__imp_GetLastError
0x18000b2f1  mov     esi, eax
0x18000b2f3  test    rbx, rbx
0x18000b2f6  jz      short loc_18000B301
0x18000b2f8  mov     rcx, rbx; hMem
0x18000b2fb  call    cs:__imp_LocalFree
0x18000b301  test    rdi, rdi
0x18000b304  jz      short loc_18000B30F
0x18000b306  mov     rcx, rdi; hMem
0x18000b309  call    cs:__imp_LocalFree
0x18000b30f  mov     ecx, esi; dwErrCode
0x18000b311  call    cs:__imp_SetLastError
0x18000b317  mov     eax, ebp
0x18000b319  add     rsp, 38h
0x18000b31d  pop     rdi
0x18000b31e  pop     rsi
0x18000b31f  pop     rbp
0x18000b320  pop     rbx
0x18000b321  retn
```
