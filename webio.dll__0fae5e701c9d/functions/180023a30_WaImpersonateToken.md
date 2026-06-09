# WaImpersonateToken

- ea: `0x180023a30`
- end: `0x180023be8`
- name: `WaImpersonateToken`
- size: `440`
- prototype: `__int64 __fastcall(HANDLE Token)`
- caller_count: `14`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f850`
- `0x18000ff50`
- `0x18001ec68`
- `0x180023410`
- `0x180024630`
- `0x180039210`
- `0x18004b5f4`
- `0x18004c10c`
- `0x180054808`
- `0x180057a90`
- `0x180057ee8`
- `0x18005d3d8`
- `0x180063854`
- `0x1800694c0`

## callees

- `0x1800180e0`
- `0x180023a30`
- `0x18002e460`
- `0x1800722f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180023aa6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180023aa6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023a7f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023a7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023a60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023a60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023afa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023afa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023bd7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023bd7`

## pseudocode

```c
__int64 __fastcall WaImpersonateToken(HANDLE Token, __int64 *a2)
{
  HANDLE CurrentThread; // rax
  __int64 v5; // rdi
  DWORD v6; // ebx
  __int64 v7; // r8
  DWORD LastError; // eax
  void *TokenHandle; // [rsp+30h] [rbp-88h] BYREF
  DWORD v11; // [rsp+38h] [rbp-80h] BYREF
  HANDLE v12; // [rsp+40h] [rbp-78h] BYREF
  __int64 v13; // [rsp+48h] [rbp-70h] BYREF
  char v14[16]; // [rsp+50h] [rbp-68h] BYREF
  HANDLE *v15; // [rsp+60h] [rbp-58h]
  __int64 v16; // [rsp+68h] [rbp-50h]
  __int64 *v17; // [rsp+70h] [rbp-48h]
  __int64 v18; // [rsp+78h] [rbp-40h]
  DWORD *v19; // [rsp+80h] [rbp-38h]
  __int64 v20; // [rsp+88h] [rbp-30h]

  TokenHandle = (void *)-1LL;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
  {
    v5 = (__int64)TokenHandle;
    v6 = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1359;
    v6 = 0;
    if ( LastError != 1008 )
      v6 = LastError;
    v5 = -(__int64)(LastError != 1008);
    TokenHandle = (void *)v5;
    if ( v6 )
      goto LABEL_6;
  }
  if ( !Token && !v5 )
  {
LABEL_19:
    *a2 = -1;
    return v6;
  }
  v6 = 0;
  if ( !SetThreadToken(0, Token) )
    v6 = WaGetLastError();
LABEL_6:
  if ( v5 != -1 && (Microsoft_Windows_WebIOEnableBits & 0x20000) != 0 )
  {
    v11 = v6;
    v15 = &v12;
    v13 = v5;
    v17 = &v13;
    v12 = Token;
    v19 = &v11;
    v16 = 8;
    v18 = 8;
    v20 = 4;
    McGenEventWrite_EventWriteTransfer(&WEB_ETW_PROVIDER_ID_Context, ThreadTokenSet, v7, 4, v14);
  }
  if ( v6 )
  {
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle((HANDLE)v5);
    goto LABEL_19;
  }
  *a2 = v5;
  return v6;
}

```

## disassembly

```asm
0x180023a30  mov     [rsp+arg_10], rbx
0x180023a35  push    rbp
0x180023a36  push    rsi
0x180023a37  push    rdi
0x180023a38  sub     rsp, 0A0h
0x180023a3f  mov     rax, cs:__security_cookie
0x180023a46  xor     rax, rsp
0x180023a49  mov     [rsp+0B8h+var_28], rax
0x180023a51  mov     rsi, rdx
0x180023a54  mov     [rsp+0B8h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180023a5d  mov     rbp, rcx
0x180023a60  call    cs:__imp_GetCurrentThread
0x180023a67  nop     dword ptr [rax+rax+00h]
0x180023a6c  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x180023a71  mov     edx, 2000Ch; DesiredAccess
0x180023a76  mov     rcx, rax; ThreadHandle
0x180023a79  mov     r8d, 1; OpenAsSelf
0x180023a7f  call    cs:__imp_OpenThreadToken
0x180023a86  nop     dword ptr [rax+rax+00h]
0x180023a8b  test    eax, eax
0x180023a8d  jz      short loc_180023AFA
0x180023a8f  mov     rdi, [rsp+0B8h+TokenHandle]
0x180023a94  xor     ebx, ebx
0x180023a96  test    rbp, rbp
0x180023a99  jz      loc_180023B33
0x180023a9f  mov     rdx, rbp; Token
0x180023aa2  xor     ecx, ecx; Thread
0x180023aa4  xor     ebx, ebx
0x180023aa6  call    cs:__imp_SetThreadToken
0x180023aad  nop     dword ptr [rax+rax+00h]
0x180023ab2  test    eax, eax
0x180023ab4  jz      loc_180023BBA
0x180023aba  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180023abe  jz      short loc_180023AC9
0x180023ac0  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+2, 2
0x180023ac7  jnz     short loc_180023B45
0x180023ac9  test    ebx, ebx
0x180023acb  jnz     loc_180023BC6
0x180023ad1  mov     [rsi], rdi
0x180023ad4  mov     eax, ebx
0x180023ad6  mov     rcx, [rsp+0B8h+var_28]
0x180023ade  xor     rcx, rsp; StackCookie
0x180023ae1  call    __security_check_cookie
0x180023ae6  mov     rbx, [rsp+0B8h+arg_10]
0x180023aee  add     rsp, 0A0h
0x180023af5  pop     rdi
0x180023af6  pop     rsi
0x180023af7  pop     rbp
0x180023af8  retn
0x180023afa  call    cs:__imp_GetLastError
0x180023b01  nop     dword ptr [rax+rax+00h]
0x180023b06  test    eax, eax
0x180023b08  mov     ecx, 54Fh
0x180023b0d  cmovz   eax, ecx
0x180023b10  xor     ebx, ebx
0x180023b12  cmp     eax, 3F0h
0x180023b17  cmovnz  ebx, eax
0x180023b1a  sub     eax, 3F0h
0x180023b1f  neg     eax
0x180023b21  sbb     rdi, rdi
0x180023b24  mov     [rsp+0B8h+TokenHandle], rdi
0x180023b29  test    ebx, ebx
0x180023b2b  jz      loc_180023A96
0x180023b31  jmp     short loc_180023ABA
0x180023b33  test    rdi, rdi
0x180023b36  jnz     loc_180023A9F
0x180023b3c  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180023b43  jmp     short loc_180023AD4
0x180023b45  lea     rax, [rsp+0B8h+var_78]
0x180023b4a  mov     [rsp+0B8h+var_80], ebx
0x180023b4e  mov     [rsp+0B8h+var_58], rax
0x180023b53  lea     rdx, ThreadTokenSet
0x180023b5a  lea     rax, [rsp+0B8h+var_70]
0x180023b5f  mov     [rsp+0B8h+var_70], rdi
0x180023b64  mov     [rsp+0B8h+var_48], rax
0x180023b69  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x180023b70  lea     rax, [rsp+0B8h+var_80]
0x180023b75  mov     [rsp+0B8h+var_78], rbp
0x180023b7a  mov     [rsp+0B8h+var_38], rax
0x180023b82  mov     r9d, 4
0x180023b88  lea     rax, [rsp+0B8h+var_68]
0x180023b8d  mov     [rsp+0B8h+var_50], 8
0x180023b96  mov     [rsp+0B8h+var_98], rax
0x180023b9b  mov     [rsp+0B8h+var_40], 8
0x180023ba4  mov     [rsp+0B8h+var_30], 4
0x180023bb0  call    McGenEventWrite_EventWriteTransfer
0x180023bb5  jmp     loc_180023AC9
0x180023bba  call    WaGetLastError
0x180023bbf  mov     ebx, eax
0x180023bc1  jmp     loc_180023ABA
0x180023bc6  lea     rax, [rdi-1]
0x180023bca  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180023bce  ja      loc_180023B3C
0x180023bd4  mov     rcx, rdi; hObject
0x180023bd7  call    cs:__imp_CloseHandle
0x180023bde  nop     dword ptr [rax+rax+00h]
0x180023be3  jmp     loc_180023B3C
```
