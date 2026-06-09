# Storage::CVolume::_UpdateSpecialFilePresence(void)

- ea: `0x1800166e0`
- end: `0x1800169d7`
- name: `?_UpdateSpecialFilePresence@CVolume@Storage@@AEAAJXZ`
- size: `759`
- prototype: `__int64 __fastcall(Storage::CVolume *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18002d4d8`

## callees

- `0x1800166e0`
- `0x18001951c`
- `0x180032c6a`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016844`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016987`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016987`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800168c3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800168c3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001695a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001695a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180016814`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180016814`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016914`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016914`

## pseudocode

```c
__int64 __fastcall Storage::CVolume::_UpdateSpecialFilePresence(Storage::CVolume *this)
{
  const WCHAR *v1; // r15
  WCHAR *v2; // r9
  __int64 v4; // rax
  WCHAR *v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r10
  __int64 v8; // rdx
  WCHAR *v9; // rcx
  WCHAR *v10; // r14
  unsigned int Error; // edi
  unsigned __int64 v12; // rsi
  __int64 v13; // rbp
  __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  wchar_t *v16; // r8
  WCHAR *v17; // rax
  WCHAR *v18; // rcx
  int v19; // eax
  _DWORD *v20; // rcx
  HANDLE FileW; // rbp
  BOOL v22; // esi
  DWORD BytesReturned[4]; // [rsp+40h] [rbp-3C8h] BYREF
  int OutBuffer; // [rsp+50h] [rbp-3B8h] BYREF
  char v26[12]; // [rsp+54h] [rbp-3B4h] BYREF
  unsigned __int16 v27; // [rsp+60h] [rbp-3A8h]
  unsigned __int16 v28; // [rsp+62h] [rbp-3A6h]
  WCHAR FileName[264]; // [rsp+1A0h] [rbp-268h] BYREF

  v1 = (const WCHAR *)((char *)this + 110);
  v2 = FileName;
  v4 = 2147483646;
  v5 = (WCHAR *)((char *)this + 110);
  v6 = 260;
  v7 = 0;
  do
  {
    if ( !v4 )
      break;
    if ( !*v5 )
      break;
    *v2++ = *v5++;
    --v4;
    ++v7;
    --v6;
  }
  while ( v6 );
  v8 = v7 - 1;
  v9 = v2 - 1;
  if ( v6 )
    v8 = v7;
  v10 = &FileName[v8];
  Error = v6 == 0 ? 0x8007007A : 0;
  if ( v6 )
    v9 = v2;
  v12 = 260 - v8;
  *v9 = 0;
  if ( v6 )
  {
    v13 = 0;
    while ( v12 )
    {
      if ( v12 <= 0x7FFFFFFF )
      {
        v14 = 2147483646;
        v15 = v12;
        v16 = (&off_180035110)[2 * v13];
        v17 = v10;
        do
        {
          if ( !v14 )
            break;
          if ( !*v16 )
            break;
          *v17++ = *v16++;
          --v14;
          --v15;
        }
        while ( v15 );
        v18 = v17 - 1;
        if ( v15 )
          v18 = v17;
        Error = v15 == 0 ? 0x8007007A : 0;
        *v18 = 0;
        goto LABEL_20;
      }
      *v10 = 0;
      Error = -2147024809;
LABEL_27:
      if ( ++v13 == 13 )
      {
        v1 = (const WCHAR *)((char *)this + 110);
        goto LABEL_29;
      }
    }
    Error = -2147024809;
LABEL_20:
    if ( (Error & 0x80000000) == 0 )
    {
      if ( GetFileAttributesW(FileName) == -1 )
      {
        if ( GetLastError() == 5 )
          *((_DWORD *)this + 12) |= 2u;
      }
      else
      {
        *((_DWORD *)this + 11) |= *((_DWORD *)&off_180035110 + 4 * v13 + 2);
      }
    }
    goto LABEL_27;
  }
LABEL_29:
  v19 = *((_DWORD *)this + 11);
  v20 = (_DWORD *)((char *)this + 52);
  if ( (v19 & 0x4808) != 0 && *v20 != 16 )
  {
    v19 &= 0xFFFFB7F7;
    *((_DWORD *)this + 11) = v19;
  }
  if ( (v19 & 0x600) != 0 && *v20 != 16 )
  {
    v19 &= 0xFFFFF9FF;
    *((_DWORD *)this + 11) = v19;
  }
  if ( (v19 & 0x4000) != 0 )
  {
    if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)this + 138, -1, L"UDF", -1) == 2 )
    {
      *((_WORD *)this + 103) = 0;
      OutBuffer = 0;
      memset_0(v26, 0, 0x14Cu);
      FileW = CreateFileW(v1, 0x80000000, 3u, 0, 3u, 0x80u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        Error = ResultFromKnownLastError();
        *((_WORD *)this + 103) = 92;
      }
      else
      {
        BytesReturned[0] = 0;
        v22 = 0;
        if ( DeviceIoControl(FileW, 0x9013Cu, 0, 0, &OutBuffer, 0x150u, BytesReturned, 0) )
        {
          if ( v27 >= 2u )
            v22 = v28 >= 5u;
        }
        else
        {
          Error = ResultFromKnownLastError();
        }
        CloseHandle(FileW);
        *((_WORD *)this + 103) = 92;
        if ( v22 )
          return Error;
      }
    }
    *((_DWORD *)this + 10) &= ~0x4000u;
  }
  return Error;
}

```

## disassembly

```asm
0x1800166e0  push    rbx
0x1800166e2  push    rbp
0x1800166e3  push    rsi
0x1800166e4  push    rdi
0x1800166e5  push    r12
0x1800166e7  push    r13
0x1800166e9  push    r14
0x1800166eb  push    r15
0x1800166ed  sub     rsp, 3C8h
0x1800166f4  mov     rax, cs:__security_cookie
0x1800166fb  xor     rax, rsp
0x1800166fe  mov     [rsp+408h+var_58], rax
0x180016706  xor     r12d, r12d
0x180016709  lea     r15, [rcx+6Eh]
0x18001670d  mov     esi, 104h
0x180016712  lea     r9, [rsp+408h+FileName]
0x18001671a  mov     rbx, rcx
0x18001671d  mov     eax, 7FFFFFFEh
0x180016722  mov     rcx, r15
0x180016725  mov     r8d, esi
0x180016728  lea     r13d, [r12+2]
0x18001672d  mov     r10d, r12d
0x180016730  test    rax, rax
0x180016733  jz      short loc_180016753
0x180016735  movzx   edx, word ptr [rcx]
0x180016738  test    dx, dx
0x18001673b  jz      short loc_180016753
0x18001673d  mov     [r9], dx
0x180016741  add     rcx, r13
0x180016744  add     r9, r13
0x180016747  dec     rax
0x18001674a  inc     r10
0x18001674d  sub     r8, 1
0x180016751  jnz     short loc_180016730
0x180016753  test    r8, r8
0x180016756  lea     rdx, [r10-1]
0x18001675a  mov     rax, r8
0x18001675d  lea     rcx, [r9-2]
0x180016761  cmovnz  rdx, r10
0x180016765  lea     r14, [rsp+408h+FileName]
0x18001676d  neg     rax
0x180016770  sbb     edi, edi
0x180016772  not     edi
0x180016774  lea     r14, [r14+rdx*2]
0x180016778  and     edi, 8007007Ah
0x18001677e  test    r8, r8
0x180016781  cmovnz  rcx, r9
0x180016785  sub     rsi, rdx
0x180016788  mov     [rcx], r12w
0x18001678c  test    r8, r8
0x18001678f  jz      loc_180016864
0x180016795  mov     rbp, r12
0x180016798  lea     r15, off_180035110; "autorun.inf"
0x18001679f  test    rsi, rsi
0x1800167a2  jz      loc_18001682F
0x1800167a8  cmp     rsi, 7FFFFFFFh
0x1800167af  ja      loc_180016839
0x1800167b5  mov     rax, rbp
0x1800167b8  mov     ecx, 7FFFFFFEh
0x1800167bd  add     rax, rax
0x1800167c0  mov     rdx, rsi
0x1800167c3  mov     r8, [r15+rax*8]
0x1800167c7  mov     rax, r14
0x1800167ca  test    rcx, rcx
0x1800167cd  jz      short loc_1800167EC
0x1800167cf  movzx   r9d, word ptr [r8]
0x1800167d3  test    r9w, r9w
0x1800167d7  jz      short loc_1800167EC
0x1800167d9  mov     [rax], r9w
0x1800167dd  add     r8, r13
0x1800167e0  add     rax, r13
0x1800167e3  dec     rcx
0x1800167e6  sub     rdx, 1
0x1800167ea  jnz     short loc_1800167CA
0x1800167ec  test    rdx, rdx
0x1800167ef  lea     rcx, [rax-2]
0x1800167f3  cmovnz  rcx, rax
0x1800167f7  neg     rdx
0x1800167fa  sbb     edi, edi
0x1800167fc  not     edi
0x1800167fe  and     edi, 8007007Ah
0x180016804  mov     [rcx], r12w
0x180016808  test    edi, edi
0x18001680a  js      short loc_180016853
0x18001680c  lea     rcx, [rsp+408h+FileName]; lpFileName
0x180016814  call    cs:__imp_GetFileAttributesW
0x18001681a  cmp     eax, 0FFFFFFFFh
0x18001681d  jz      short loc_180016844
0x18001681f  mov     rax, rbp
0x180016822  add     rax, rax
0x180016825  mov     eax, [r15+rax*8+8]
0x18001682a  or      [rbx+2Ch], eax
0x18001682d  jmp     short loc_180016853
0x18001682f  mov     edi, 80070057h
0x180016834  test    rsi, rsi
0x180016837  jz      short loc_180016808
0x180016839  mov     [r14], r12w
0x18001683d  mov     edi, 80070057h
0x180016842  jmp     short loc_180016853
0x180016844  call    cs:__imp_GetLastError
0x18001684a  cmp     eax, 5
0x18001684d  jnz     short loc_180016853
0x18001684f  or      [rbx+30h], r13d
0x180016853  inc     rbp
0x180016856  cmp     rbp, 0Dh
0x18001685a  jnz     loc_18001679F
0x180016860  lea     r15, [rbx+6Eh]
0x180016864  mov     eax, [rbx+2Ch]
0x180016867  lea     rcx, [rbx+34h]
0x18001686b  test    eax, 4808h
0x180016870  jz      short loc_18001687F
0x180016872  cmp     dword ptr [rcx], 10h
0x180016875  jz      short loc_18001687F
0x180016877  and     eax, 0FFFFB7F7h
0x18001687c  mov     [rbx+2Ch], eax
0x18001687f  test    eax, 600h
0x180016884  jz      short loc_180016893
0x180016886  cmp     dword ptr [rcx], 10h
0x180016889  jz      short loc_180016893
0x18001688b  and     eax, 0FFFFF9FFh
0x180016890  mov     [rbx+2Ch], eax
0x180016893  bt      eax, 0Eh
0x180016897  jnb     loc_1800169B1
0x18001689d  or      r9d, 0FFFFFFFFh; cchCount1
0x1800168a1  mov     [rsp+408h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800168a9  lea     rax, aUdf; "UDF"
0x1800168b0  lea     r8, [rbx+114h]; lpString1
0x1800168b7  mov     [rsp+408h+lpString2], rax; lpString2
0x1800168bc  lea     edx, [r9+2]; dwCmpFlags
0x1800168c0  lea     ecx, [rdx+7Eh]; Locale
0x1800168c3  call    cs:__imp_CompareStringW
0x1800168c9  cmp     eax, r13d
0x1800168cc  jnz     loc_1800169AC
0x1800168d2  xor     edx, edx; Val
0x1800168d4  mov     [rbx+0CEh], r12w
0x1800168dc  mov     r8d, 14Ch; Size
0x1800168e2  mov     [rsp+408h+OutBuffer], r12d
0x1800168e7  lea     rcx, [rsp+408h+var_3B4]; void *
0x1800168ec  call    memset_0
0x1800168f1  mov     r8d, 3; dwShareMode
0x1800168f7  mov     [rsp+408h+hTemplateFile], r12; hTemplateFile
0x1800168fc  mov     [rsp+408h+cchCount2], 80h; dwFlagsAndAttributes
0x180016904  xor     r9d, r9d; lpSecurityAttributes
0x180016907  mov     edx, 80000000h; dwDesiredAccess
0x18001690c  mov     dword ptr [rsp+408h+lpString2], r8d; dwCreationDisposition
0x180016911  mov     rcx, r15; lpFileName
0x180016914  call    cs:__imp_CreateFileW
0x18001691a  mov     rbp, rax
0x18001691d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016921  jz      short loc_18001699C
0x180016923  mov     [rsp+408h+lpOverlapped], r12; lpOverlapped
0x180016928  lea     rax, [rsp+408h+BytesReturned]
0x18001692d  mov     [rsp+408h+hTemplateFile], rax; lpBytesReturned
0x180016932  xor     r9d, r9d; nInBufferSize
0x180016935  lea     rax, [rsp+408h+OutBuffer]
0x18001693a  mov     [rsp+408h+cchCount2], 150h; nOutBufferSize
0x180016942  xor     r8d, r8d; lpInBuffer
0x180016945  mov     [rsp+408h+lpString2], rax; lpOutBuffer
0x18001694a  mov     edx, 9013Ch; dwIoControlCode
0x18001694f  mov     [rsp+408h+BytesReturned], r12d
0x180016954  mov     rcx, rbp; hDevice
0x180016957  mov     esi, r12d
0x18001695a  call    cs:__imp_DeviceIoControl
0x180016960  test    eax, eax
0x180016962  jz      short loc_18001697D
0x180016964  cmp     [rsp+408h+var_3A8], r13w
0x18001696a  jb      short loc_180016984
0x18001696c  mov     eax, 5
0x180016971  cmp     [rsp+408h+var_3A6], ax
0x180016976  jb      short loc_180016984
0x180016978  lea     esi, [rax-4]
0x18001697b  jmp     short loc_180016984
0x18001697d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180016982  mov     edi, eax
0x180016984  mov     rcx, rbp; hObject
0x180016987  call    cs:__imp_CloseHandle
0x18001698d  mov     word ptr [rbx+0CEh], 5Ch ; '\'
0x180016996  test    esi, esi
0x180016998  jz      short loc_1800169AC
0x18001699a  jmp     short loc_1800169B1
0x18001699c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800169a1  mov     edi, eax
0x1800169a3  mov     word ptr [rbx+0CEh], 5Ch ; '\'
0x1800169ac  btr     dword ptr [rbx+28h], 0Eh
0x1800169b1  mov     eax, edi
0x1800169b3  mov     rcx, [rsp+408h+var_58]
0x1800169bb  xor     rcx, rsp; StackCookie
0x1800169be  call    __security_check_cookie
0x1800169c3  add     rsp, 3C8h
0x1800169ca  pop     r15
0x1800169cc  pop     r14
0x1800169ce  pop     r13
0x1800169d0  pop     r12
0x1800169d2  pop     rdi
0x1800169d3  pop     rsi
0x1800169d4  pop     rbp
0x1800169d5  pop     rbx
0x1800169d6  retn
```
