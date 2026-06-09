# ValidateContainerDirectory(ushort const *,int *)

- ea: `0x1800201e8`
- end: `0x18002045f`
- name: `?ValidateContainerDirectory@@YAJPEBGPEAH@Z`
- size: `631`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18001f5fc`
- `0x1800259c0`
- `0x1801bfa74`
- `0x1801c3668`

## callees

- `0x1800201e8`
- `0x180020468`
- `0x1800204f8`
- `0x18002086c`
- `0x180027ec0`
- `0x1800701d0`
- `0x1801e1790`
- `0x1801e2388`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800202d1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800202d1`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002040f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002040f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180020308`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180020308`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800202ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800203a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800202ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800203a0`
- `RPCRT4!RpcRevertToSelf` at `0x180020356`
- `RPCRT4!RpcRevertToSelf` at `0x180020356`

## pseudocode

```c
__int64 __fastcall ValidateContainerDirectory(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  const WCHAR *v2; // rbp
  int v5; // eax
  signed int LastError; // edi
  HANDLE FileW; // rbx
  __int64 v8; // rdx
  __int64 v9; // rcx
  BOOL v10; // r15d
  DWORD FileAttributesW; // eax
  unsigned int v12; // esi
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  const unsigned __int16 *dwCreationDisposition; // [rsp+20h] [rbp-88h]
  const unsigned __int16 *dwFlagsAndAttributes; // [rsp+28h] [rbp-80h]
  const unsigned __int16 *hTemplateFile; // [rsp+30h] [rbp-78h]
  const unsigned __int16 *v20; // [rsp+38h] [rbp-70h]
  const unsigned __int16 *v21; // [rsp+40h] [rbp-68h]
  const unsigned __int16 *v22; // [rsp+48h] [rbp-60h]
  const unsigned __int16 *v23; // [rsp+50h] [rbp-58h]
  const WCHAR *v24; // [rsp+60h] [rbp-48h] BYREF
  int v25; // [rsp+68h] [rbp-40h] BYREF
  LPCWSTR lpFileName[7]; // [rsp+70h] [rbp-38h] BYREF

  HIDWORD(v24) = 0;
  v2 = &Data;
  lpFileName[0] = &Data;
  v25 = 0;
  lpFileName[1] = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_Sq(1036, 10, (unsigned int)WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids, (_DWORD)a1, (__int64)a2);
  if ( a2 )
    *(_DWORD *)a2 = 0;
  v5 = WxRpcImpersonateNonElevatedCaller(&v25);
  LastError = v5;
  if ( v5 < 0 )
  {
    HIDWORD(v24) = 72;
LABEL_28:
    v12 = v5;
    goto LABEL_15;
  }
  v5 = WxValidateCacheDirectory(a1);
  LastError = v5;
  if ( v5 < 0 )
  {
    HIDWORD(v24) = 77;
    goto LABEL_28;
  }
  v5 = CWxString::SetPath(
         (CWxString *)lpFileName,
         a1,
         L"container.dat",
         0,
         dwCreationDisposition,
         dwFlagsAndAttributes,
         hTemplateFile,
         v20,
         v21,
         v22,
         v23);
  v2 = lpFileName[0];
  LastError = v5;
  if ( v5 < 0 )
  {
    HIDWORD(v24) = 84;
    goto LABEL_28;
  }
  FileW = CreateFileW(lpFileName[0], 0x100000u, 7u, 0, 4u, 0, 0);
  LastError = WxGetLastError(v9, v8);
  if ( FileW == (HANDLE)-1LL )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    HIDWORD(v24) = 93;
    goto LABEL_26;
  }
  CloseHandle(FileW);
  v10 = LastError != 183;
  FileAttributesW = GetFileAttributesW(v2);
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) != 0 )
  {
    LastError = -2147024893;
    HIDWORD(v24) = 112;
LABEL_26:
    v12 = LastError;
    goto LABEL_15;
  }
  HIDWORD(v24) = 0;
  if ( (FileAttributesW & 0x2006) == 0x2006 || SetFileAttributesW(v2, FileAttributesW | 0x2006) )
  {
    LastError = 0;
  }
  else
  {
    v16 = WxGetLastError(v15, v14);
    LastError = v16;
    if ( v16 > 0 )
      LastError = (unsigned __int16)v16 | 0x80070000;
    HIDWORD(v24) = 429;
    if ( LastError >= 0 )
      LastError = -2147418113;
  }
  v12 = LastError;
  if ( LastError < 0 )
    HIDWORD(v24) = 115;
  else
    *(_DWORD *)a2 = v10;
LABEL_15:
  if ( v25 )
    RpcRevertToSelf();
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 11, WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids, (unsigned int)LastError);
  v24 = v2;
  if ( v2 != &Data && v2 )
    WxFreeHeapEx(&v24);
  return v12;
}

```

## disassembly

```asm
0x1800201e8  mov     rax, rsp
0x1800201eb  mov     [rax+18h], rbx
0x1800201ef  push    rbp
0x1800201f0  push    rsi
0x1800201f1  push    rdi
0x1800201f2  push    r14
0x1800201f4  push    r15
0x1800201f6  sub     rsp, 80h
0x1800201fd  lea     r15, Data
0x180020204  mov     [rsp+0A8h+var_44], 0
0x18002020c  mov     rbp, r15
0x18002020f  mov     [rax-38h], r15
0x180020213  mov     r14, rdx
0x180020216  mov     dword ptr [rax-40h], 0
0x18002021d  mov     rsi, rcx
0x180020220  mov     qword ptr [rax-30h], 0
0x180020228  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002022c  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180020233  jz      short loc_180020251
0x180020235  lea     edx, [rbx+0Bh]
0x180020238  mov     qword ptr [rsp+0A8h+dwCreationDisposition], r14; unsigned __int16 *
0x18002023d  mov     ecx, 40Ch
0x180020242  lea     r8, WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids
0x180020249  mov     r9, rsi
0x18002024c  call    WPP_SF_Sq
0x180020251  test    r14, r14
0x180020254  jz      short loc_18002025D
0x180020256  mov     dword ptr [r14], 0
0x18002025d  lea     rcx, [rsp+0A8h+var_40]; int *
0x180020262  call    ?WxRpcImpersonateNonElevatedCaller@@YAJPEAH@Z; WxRpcImpersonateNonElevatedCaller(int *)
0x180020267  mov     edi, eax
0x180020269  test    eax, eax
0x18002026b  js      loc_1800203DB
0x180020271  mov     rcx, rsi; unsigned __int16 *
0x180020274  call    ?WxValidateCacheDirectory@@YAJPEBG@Z; WxValidateCacheDirectory(ushort const *)
0x180020279  mov     edi, eax
0x18002027b  test    eax, eax
0x18002027d  js      loc_180020448
0x180020283  xor     r9d, r9d; unsigned __int16 *
0x180020286  lea     r8, ?c_wszContainerCanaryFile@@3QBGB; "container.dat"
0x18002028d  mov     rdx, rsi; unsigned __int16 *
0x180020290  lea     rcx, [rsp+0A8h+lpFileName]; this
0x180020295  call    ?SetPath@CWxString@@QEAAJPEBG000000000@Z; CWxString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18002029a  mov     rbp, [rsp+0A8h+lpFileName]
0x18002029f  mov     edi, eax
0x1800202a1  test    eax, eax
0x1800202a3  js      loc_180020400
0x1800202a9  xor     r9d, r9d; lpSecurityAttributes
0x1800202ac  mov     [rsp+0A8h+hTemplateFile], 0; hTemplateFile
0x1800202b5  mov     dword ptr [rsp+0A8h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800202bd  mov     edx, 100000h; dwDesiredAccess
0x1800202c2  mov     rcx, rbp; lpFileName
0x1800202c5  mov     [rsp+0A8h+dwCreationDisposition], 4; dwCreationDisposition
0x1800202cd  lea     r8d, [r9+7]; dwShareMode
0x1800202d1  call    cs:__imp_CreateFileW
0x1800202d7  mov     rbx, rax
0x1800202da  call    WxGetLastError
0x1800202df  mov     edi, eax
0x1800202e1  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800202e5  jz      loc_1800203BF
0x1800202eb  mov     rcx, rbx; hObject
0x1800202ee  call    cs:__imp_CloseHandle
0x1800202f4  xor     r15d, r15d
0x1800202f7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800202fb  cmp     edi, 0B7h
0x180020301  mov     rcx, rbp; lpFileName
0x180020304  setnz   r15b
0x180020308  call    cs:__imp_GetFileAttributesW
0x18002030e  mov     edx, eax
0x180020310  cmp     eax, 0FFFFFFFFh
0x180020313  jz      loc_1800203EA
0x180020319  test    dl, 10h
0x18002031c  jnz     loc_1800203EA
0x180020322  mov     ecx, 2006h
0x180020327  mov     [rsp+0A8h+var_44], 0
0x18002032f  and     eax, ecx
0x180020331  cmp     eax, ecx
0x180020333  jnz     loc_18002040A
0x180020339  xor     edi, edi
0x18002033b  mov     esi, edi
0x18002033d  test    edi, edi
0x18002033f  js      loc_180020452
0x180020345  mov     [r14], r15d
0x180020348  lea     r15, Data
0x18002034f  cmp     [rsp+0A8h+var_40], 0
0x180020354  jz      short loc_18002035C
0x180020356  call    cs:__imp_RpcRevertToSelf
0x18002035c  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180020363  jz      short loc_18002037E
0x180020365  mov     edx, 0Bh
0x18002036a  lea     r8, WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids
0x180020371  mov     ecx, 40Ch
0x180020376  mov     r9d, edi
0x180020379  call    WPP_SF_d
0x18002037e  mov     [rsp+60h], rbp
0x180020383  cmp     rbp, r15
0x180020386  jz      short loc_180020397
0x180020388  test    rbp, rbp
0x18002038b  jz      short loc_180020397
0x18002038d  lea     rcx, [rsp+0A8h+var_48]
0x180020392  call    WxFreeHeapEx
0x180020397  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002039b  jz      short loc_1800203A6
0x18002039d  mov     rcx, rbx; hObject
0x1800203a0  call    cs:__imp_CloseHandle
0x1800203a6  mov     rbx, [rsp+0A8h+arg_10]
0x1800203ae  mov     eax, esi
0x1800203b0  add     rsp, 80h
0x1800203b7  pop     r15
0x1800203b9  pop     r14
0x1800203bb  pop     rdi
0x1800203bc  pop     rsi
0x1800203bd  pop     rbp
0x1800203be  retn
0x1800203bf  test    edi, edi
0x1800203c1  jle     short loc_1800203CC
0x1800203c3  movzx   edi, di
0x1800203c6  or      edi, 80070000h
0x1800203cc  mov     [rsp+0A8h+var_44], 5Dh ; ']'
0x1800203d4  mov     esi, edi
0x1800203d6  jmp     loc_18002034F
0x1800203db  mov     [rsp+0A8h+var_44], 48h ; 'H'
0x1800203e3  mov     esi, eax
0x1800203e5  jmp     loc_18002034F
0x1800203ea  mov     edi, 80070003h
0x1800203ef  mov     [rsp+0A8h+var_44], 70h ; 'p'
0x1800203f7  lea     r15, Data
0x1800203fe  jmp     short loc_1800203D4
0x180020400  mov     [rsp+0A8h+var_44], 54h ; 'T'
0x180020408  jmp     short loc_1800203E3
0x18002040a  or      edx, ecx; dwFileAttributes
0x18002040c  mov     rcx, rbp; lpFileName
0x18002040f  call    cs:__imp_SetFileAttributesW
0x180020415  test    eax, eax
0x180020417  jnz     loc_180020339
0x18002041d  call    WxGetLastError
0x180020422  mov     edi, eax
0x180020424  test    eax, eax
0x180020426  jle     short loc_180020431
0x180020428  movzx   edi, ax
0x18002042b  or      edi, 80070000h
0x180020431  test    edi, edi
0x180020433  mov     [rsp+0A8h+var_44], 1ADh
0x18002043b  mov     eax, 8000FFFFh
0x180020440  cmovns  edi, eax
0x180020443  jmp     loc_18002033B
0x180020448  mov     [rsp+0A8h+var_44], 4Dh ; 'M'
0x180020450  jmp     short loc_1800203E3
0x180020452  mov     [rsp+0A8h+var_44], 73h ; 's'
0x18002045a  jmp     loc_180020348
```
