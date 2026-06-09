# WTSCreateListenerA

- ea: `0x18000a490`
- end: `0x18000a577`
- name: `WTSCreateListenerA`
- size: `231`
- prototype: `BOOL __stdcall(HANDLE hServer, PVOID pReserved, DWORD Reserved, LPSTR pListenerName, PWTSLISTENERCONFIGA pBuffer, DWORD flag)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180008acc`
- `0x18000a188`
- `0x18000a490`
- `0x18000a580`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a531`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a55f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a531`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a55f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a537`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a549`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a557`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a549`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a557`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a4ef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a4ef`

## pseudocode

```c
BOOL __stdcall WTSCreateListenerA(
        HANDLE hServer,
        PVOID pReserved,
        DWORD Reserved,
        LPSTR pListenerName,
        PWTSLISTENERCONFIGA pBuffer,
        DWORD flag)
{
  BOOL v6; // ebp
  struct _WTSLISTENERCONFIGW *v7; // rbx
  DWORD v8; // edi
  struct _WTSLISTENERCONFIGW *v9; // rax
  DWORD LastError; // edi
  LPWSTR pListenerNamea; // [rsp+40h] [rbp+8h] BYREF

  v6 = 0;
  v7 = 0;
  pListenerNamea = 0;
  if ( hServer )
    goto LABEL_12;
  if ( pReserved )
    goto LABEL_12;
  if ( Reserved )
    goto LABEL_12;
  if ( !pListenerName )
    goto LABEL_12;
  if ( !pBuffer )
    goto LABEL_12;
  v8 = flag;
  if ( flag != 1 && flag != 16 )
    goto LABEL_12;
  if ( !(unsigned int)CopyStringA((__int64)pListenerName, &pListenerNamea, 0) )
    goto LABEL_12;
  v9 = (struct _WTSLISTENERCONFIGW *)LocalAlloc(0x40u, 0x544u);
  v7 = v9;
  if ( !v9 )
    goto LABEL_13;
  if ( (unsigned int)ConvertListenerConfigFromAnsiToUnicode(pBuffer, v9) )
    v6 = WTSCreateListenerW(0, 0, 0, pListenerNamea, v7, v8);
  else
LABEL_12:
    SetLastError(0x57u);
LABEL_13:
  LastError = GetLastError();
  if ( pListenerNamea )
    LocalFree(pListenerNamea);
  if ( v7 )
    LocalFree(v7);
  SetLastError(LastError);
  return v6;
}

```

## disassembly

```asm
0x18000a490  mov     [rsp+arg_8], rbx
0x18000a495  mov     [rsp+arg_10], rbp
0x18000a49a  push    rdi
0x18000a49b  sub     rsp, 30h
0x18000a49f  xor     ebp, ebp
0x18000a4a1  xor     ebx, ebx
0x18000a4a3  mov     [rsp+38h+pListenerName], rbp
0x18000a4a8  test    rcx, rcx
0x18000a4ab  jnz     short loc_18000A52C
0x18000a4ad  test    rdx, rdx
0x18000a4b0  jnz     short loc_18000A52C
0x18000a4b2  test    r8d, r8d
0x18000a4b5  jnz     short loc_18000A52C
0x18000a4b7  test    r9, r9
0x18000a4ba  jz      short loc_18000A52C
0x18000a4bc  cmp     [rsp+38h+pBuffer], rbx
0x18000a4c1  jz      short loc_18000A52C
0x18000a4c3  mov     edi, [rsp+38h+flag]
0x18000a4c7  cmp     edi, 1
0x18000a4ca  jz      short loc_18000A4D1
0x18000a4cc  cmp     edi, 10h
0x18000a4cf  jnz     short loc_18000A52C
0x18000a4d1  xor     r8d, r8d
0x18000a4d4  lea     rdx, [rsp+38h+pListenerName]
0x18000a4d9  mov     rcx, r9
0x18000a4dc  call    _CopyStringA
0x18000a4e1  test    eax, eax
0x18000a4e3  jz      short loc_18000A52C
0x18000a4e5  mov     edx, 544h; uBytes
0x18000a4ea  mov     ecx, 40h ; '@'; uFlags
0x18000a4ef  call    cs:__imp_LocalAlloc
0x18000a4f5  mov     rbx, rax
0x18000a4f8  test    rax, rax
0x18000a4fb  jz      short loc_18000A537
0x18000a4fd  mov     rcx, [rsp+38h+pBuffer]
0x18000a502  mov     rdx, rax
0x18000a505  call    ConvertListenerConfigFromAnsiToUnicode
0x18000a50a  test    eax, eax
0x18000a50c  jz      short loc_18000A52C
0x18000a50e  mov     r9, [rsp+38h+pListenerName]; pListenerName
0x18000a513  xor     r8d, r8d; Reserved
0x18000a516  mov     [rsp+38h+var_10], edi; flag
0x18000a51a  xor     edx, edx; pReserved
0x18000a51c  xor     ecx, ecx; hServer
0x18000a51e  mov     [rsp+38h+var_18], rbx; pBuffer
0x18000a523  call    WTSCreateListenerW
0x18000a528  mov     ebp, eax
0x18000a52a  jmp     short loc_18000A537
0x18000a52c  mov     ecx, 57h ; 'W'; dwErrCode
0x18000a531  call    cs:__imp_SetLastError
0x18000a537  call    cs:__imp_GetLastError
0x18000a53d  mov     rcx, [rsp+38h+pListenerName]; hMem
0x18000a542  mov     edi, eax
0x18000a544  test    rcx, rcx
0x18000a547  jz      short loc_18000A54F
0x18000a549  call    cs:__imp_LocalFree
0x18000a54f  test    rbx, rbx
0x18000a552  jz      short loc_18000A55D
0x18000a554  mov     rcx, rbx; hMem
0x18000a557  call    cs:__imp_LocalFree
0x18000a55d  mov     ecx, edi; dwErrCode
0x18000a55f  call    cs:__imp_SetLastError
0x18000a565  mov     rbx, [rsp+38h+arg_8]
0x18000a56a  mov     eax, ebp
0x18000a56c  mov     rbp, [rsp+38h+arg_10]
0x18000a571  add     rsp, 30h
0x18000a575  pop     rdi
0x18000a576  retn
```
