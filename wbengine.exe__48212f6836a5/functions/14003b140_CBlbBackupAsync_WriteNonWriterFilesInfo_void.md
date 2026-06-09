# CBlbBackupAsync::WriteNonWriterFilesInfo(void)

- ea: `0x14003b140`
- end: `0x14003b4de`
- name: `?WriteNonWriterFilesInfo@CBlbBackupAsync@@AEAAJXZ`
- size: `926`
- prototype: `__int64 __fastcall(CBlbBackupAsync *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, service_task`

## callers

- `0x140039ec0`

## callees

- `0x140006ca8`
- `0x140006d94`
- `0x140008ac8`
- `0x14000bb4c`
- `0x14000fe94`
- `0x140014260`
- `0x140014384`
- `0x140014798`
- `0x140028eb8`
- `0x140035350`
- `0x14003b140`
- `0x1400889f0`
- `0x1400f25c0`
- `0x1400f3bbc`
- `0x14011f430`
- `0x14011ff3c`
- `0x140137010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x14003b247`
- `KERNEL32!DeleteFileW` at `0x14003b247`
- `KERNEL32!GetLastError` at `0x14003b251`
- `KERNEL32!GetLastError` at `0x14003b251`
- `ole32!CoTaskMemFree` at `0x14003b41a`
- `ole32!CoTaskMemFree` at `0x14003b436`
- `ole32!CoTaskMemFree` at `0x14003b44b`
- `ole32!CoTaskMemFree` at `0x14003b464`
- `ole32!CoTaskMemFree` at `0x14003b4c5`
- `ole32!CoTaskMemFree` at `0x14003b41a`
- `ole32!CoTaskMemFree` at `0x14003b436`
- `ole32!CoTaskMemFree` at `0x14003b44b`
- `ole32!CoTaskMemFree` at `0x14003b464`
- `ole32!CoTaskMemFree` at `0x14003b4c5`

## string_xrefs

- `0x14003b18d`: `base\stor\blb\engine\service\backup.cpp`
- `0x14003b181`: `m_wszBackupSetDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBlbBackupAsync::WriteNonWriterFilesInfo(CBlbBackupAsync *this)
{
  unsigned __int16 *v2; // r13
  WCHAR *v3; // rsi
  unsigned __int16 *v4; // r12
  CBlbFileVerifier *v5; // r15
  signed int appended; // ebx
  int v7; // r14d
  PVOID *v8; // rcx
  DWORD LastError; // eax
  int v10; // eax
  void *v11; // r14
  void *v12; // rax
  __int64 v13; // r8
  _QWORD *v14; // rdi
  unsigned __int64 v15; // r15
  CBlbFileVerifier *v16; // rcx
  unsigned __int16 *v18; // [rsp+30h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+90h] [rbp+48h] BYREF
  LPCWSTR lpFileName; // [rsp+98h] [rbp+50h] BYREF
  unsigned __int16 *v21; // [rsp+A0h] [rbp+58h] BYREF
  unsigned __int16 *v22; // [rsp+A8h] [rbp+60h] BYREF

  v2 = 0;
  v21 = 0;
  v18 = 0;
  v3 = 0;
  lpFileName = 0;
  v4 = 0;
  v22 = 0;
  pv = 0;
  v5 = 0;
  if ( !*((_QWORD *)this + 59) )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x1EA8u, "m_wszBackupSetDirectory");
  if ( (*((_BYTE *)this + 340) & 4) == 0 )
    goto LABEL_19;
  appended = BlbAppendNonWriterInfoFile(*((unsigned __int16 **)this + 59), 0, 0, &v18);
  if ( appended < 0 )
  {
LABEL_47:
    v8 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_48;
  }
  v7 = (int)v18;
  appended = BlbFindFile(v18, (unsigned __int16 **)&lpFileName);
  if ( appended < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      v3 = (WCHAR *)lpFileName;
      goto LABEL_43;
    }
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      366,
      (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
      v7,
      *((_QWORD *)this + 59),
      appended);
    v3 = (WCHAR *)lpFileName;
    goto LABEL_42;
  }
  v3 = (WCHAR *)lpFileName;
  if ( !lpFileName || DeleteFileW(lpFileName) )
  {
LABEL_19:
    appended = BlbAppendNonWriterInfoFile(*((unsigned __int16 **)this + 59), (UUID *)((char *)this + 296), 0, &v22);
    v4 = v22;
    if ( appended >= 0 )
    {
      if ( (*((_BYTE *)this + 340) & 1) != 0 )
        v10 = BlbutilDuplicateString(v22, (unsigned __int16 **)&pv, 0);
      else
        v10 = BlbAppendNonWriterInfoFile(
                *((unsigned __int16 **)this + 59),
                (UUID *)((char *)this + 296),
                1u,
                (unsigned __int16 **)&pv);
      appended = v10;
      if ( v10 < 0 )
      {
        v11 = pv;
      }
      else
      {
        appended = BlbCreateNonWriterXML(&v21);
        v2 = v21;
        v11 = pv;
        if ( appended >= 0 )
        {
          appended = BlbSafeDumpFile(v4, pv, *((unsigned int *)this + 84), v21);
          if ( appended >= 0 && *((char *)this + 340) < 0 && *((_BYTE *)this + 276) )
          {
            v12 = operator new(0x40u);
            pv = v12;
            v5 = v12 ? CBlbFileVerifier::CBlbFileVerifier((CBlbFileVerifier *)v12) : 0LL;
            pv = v5;
            appended = CBlbFileVerifier::Init(v5, v4);
            if ( appended >= 0 )
            {
              v13 = -1;
              do
                ++v13;
              while ( v2[v13] );
              appended = CBlbFileVerifier::SetChecksumForData(v5, v2, 2 * v13 + 2);
              if ( appended >= 0 )
              {
                v14 = (_QWORD *)((char *)this + 776);
                v15 = v14[1];
                if ( v15 >= v14[2]
                  && !(unsigned __int8)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(
                                         v14,
                                         v15 + 1) )
                {
                  ATL::AtlThrowImpl(-2147024882);
                }
                v16 = (CBlbFileVerifier *)pv;
                *(_QWORD *)(*v14 + 8 * v15) = pv;
                ++v14[1];
                v5 = v16;
              }
            }
          }
        }
      }
      if ( v11 )
        CoTaskMemFree(v11);
    }
LABEL_42:
    v8 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_43;
  }
  LastError = GetLastError();
  appended = LastError;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      367,
      (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
      (_DWORD)v3,
      LastError);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( appended > 0 )
    appended = (unsigned __int16)appended | 0x80070000;
LABEL_43:
  if ( v3 )
  {
    CoTaskMemFree(v3);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 )
  {
    CoTaskMemFree(v4);
    goto LABEL_47;
  }
LABEL_48:
  if ( v18 )
  {
    CoTaskMemFree(v18);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( appended < 0 )
  {
    if ( v5 )
    {
      (**(void (__fastcall ***)(CBlbFileVerifier *, __int64))v5)(v5, 1);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 2u )
      WPP_SF_d(v8[2], 368, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  if ( v2 )
    CoTaskMemFree(v2);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14003b140  push    rbp
0x14003b142  push    rbx
0x14003b143  push    rsi
0x14003b144  push    rdi
0x14003b145  push    r12
0x14003b147  push    r13
0x14003b149  push    r14
0x14003b14b  push    r15
0x14003b14d  mov     rbp, rsp
0x14003b150  sub     rsp, 48h
0x14003b154  mov     rdi, rcx
0x14003b157  xor     eax, eax
0x14003b159  mov     r13d, eax
0x14003b15c  mov     [rbp+arg_10], rax
0x14003b160  mov     [rbp+var_18], rax
0x14003b164  mov     esi, eax
0x14003b166  mov     [rbp+lpFileName], rax
0x14003b16a  mov     r12d, eax
0x14003b16d  mov     [rbp+arg_18], rax
0x14003b171  mov     [rbp+pv], rax
0x14003b175  mov     r15d, eax
0x14003b178  cmp     [rcx+1D8h], rax
0x14003b17f  jnz     short loc_14003B199
0x14003b181  lea     r8, aMWszbackupsetd; "m_wszBackupSetDirectory"
0x14003b188  mov     edx, 1EA8h; unsigned int
0x14003b18d  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x14003b194  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14003b199  lea     r14, WPP_GLOBAL_Control
0x14003b1a0  test    byte ptr [rdi+154h], 4
0x14003b1a7  jz      loc_14003B2B1
0x14003b1ad  lea     r9, [rbp+var_18]; unsigned __int16 **
0x14003b1b1  xor     r8d, r8d; unsigned __int8
0x14003b1b4  xor     edx, edx; Uuid
0x14003b1b6  mov     rcx, [rdi+1D8h]; unsigned __int16 *
0x14003b1bd  call    ?BlbAppendNonWriterInfoFile@@YAJPEAGPEAU_GUID@@EPEAPEAG@Z; BlbAppendNonWriterInfoFile(ushort *,_GUID *,uchar,ushort * *)
0x14003b1c2  mov     ebx, eax
0x14003b1c4  test    eax, eax
0x14003b1c6  js      loc_14003B451
0x14003b1cc  lea     rdx, [rbp+lpFileName]; unsigned __int16 **
0x14003b1d0  mov     r14, [rbp+var_18]
0x14003b1d4  mov     rcx, r14; unsigned __int16 *
0x14003b1d7  call    ?BlbFindFile@@YAJPEAGPEAPEAG@Z; BlbFindFile(ushort *,ushort * *)
0x14003b1dc  mov     ebx, eax
0x14003b1de  test    eax, eax
0x14003b1e0  jns     short loc_14003B23B
0x14003b1e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b1e9  lea     rax, WPP_GLOBAL_Control
0x14003b1f0  cmp     rcx, rax
0x14003b1f3  jz      short loc_14003B232
0x14003b1f5  test    byte ptr [rcx+1Ch], 1
0x14003b1f9  jz      short loc_14003B232
0x14003b1fb  cmp     byte ptr [rcx+19h], 2
0x14003b1ff  jb      short loc_14003B232
0x14003b201  mov     edx, 16Eh
0x14003b206  mov     [rsp+48h+var_20], ebx
0x14003b20a  mov     rax, [rdi+1D8h]
0x14003b211  mov     [rsp+48h+var_28], rax
0x14003b216  mov     r9, r14
0x14003b219  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003b220  mov     rcx, [rcx+10h]
0x14003b224  call    WPP_SF_SSD
0x14003b229  mov     rsi, [rbp+lpFileName]
0x14003b22d  jmp     loc_14003B420
0x14003b232  mov     rsi, [rbp+lpFileName]
0x14003b236  jmp     loc_14003B427
0x14003b23b  mov     rsi, [rbp+lpFileName]
0x14003b23f  test    rsi, rsi
0x14003b242  jz      short loc_14003B2B1
0x14003b244  mov     rcx, rsi; lpFileName
0x14003b247  call    cs:__imp_DeleteFileW
0x14003b24d  test    eax, eax
0x14003b24f  jnz     short loc_14003B2B1
0x14003b251  call    cs:__imp_GetLastError
0x14003b257  mov     ebx, eax
0x14003b259  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b260  lea     r14, WPP_GLOBAL_Control
0x14003b267  cmp     rcx, r14
0x14003b26a  jz      short loc_14003B29B
0x14003b26c  test    byte ptr [rcx+1Ch], 1
0x14003b270  jz      short loc_14003B29B
0x14003b272  cmp     byte ptr [rcx+19h], 2
0x14003b276  jb      short loc_14003B29B
0x14003b278  mov     edx, 16Fh
0x14003b27d  mov     dword ptr [rsp+48h+var_28], eax
0x14003b281  mov     r9, rsi
0x14003b284  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003b28b  mov     rcx, [rcx+10h]
0x14003b28f  call    WPP_SF_Sd
0x14003b294  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b29b  test    ebx, ebx
0x14003b29d  jle     loc_14003B42E
0x14003b2a3  movzx   ebx, bx
0x14003b2a6  or      ebx, 80070000h
0x14003b2ac  jmp     loc_14003B42E
0x14003b2b1  lea     r14, [rdi+128h]
0x14003b2b8  lea     r9, [rbp+arg_18]; unsigned __int16 **
0x14003b2bc  xor     r8d, r8d; unsigned __int8
0x14003b2bf  mov     rdx, r14; Uuid
0x14003b2c2  mov     rcx, [rdi+1D8h]; unsigned __int16 *
0x14003b2c9  call    ?BlbAppendNonWriterInfoFile@@YAJPEAGPEAU_GUID@@EPEAPEAG@Z; BlbAppendNonWriterInfoFile(ushort *,_GUID *,uchar,ushort * *)
0x14003b2ce  mov     ebx, eax
0x14003b2d0  mov     r12, [rbp+arg_18]
0x14003b2d4  test    eax, eax
0x14003b2d6  js      loc_14003B420
0x14003b2dc  test    byte ptr [rdi+154h], 1
0x14003b2e3  jz      short loc_14003B2F6
0x14003b2e5  xor     r8d, r8d; unsigned __int64
0x14003b2e8  lea     rdx, [rbp+pv]; unsigned __int16 **
0x14003b2ec  mov     rcx, r12; unsigned __int16 *
0x14003b2ef  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14003b2f4  jmp     short loc_14003B30C
0x14003b2f6  lea     r9, [rbp+pv]; unsigned __int16 **
0x14003b2fa  mov     r8b, 1; unsigned __int8
0x14003b2fd  mov     rdx, r14; Uuid
0x14003b300  mov     rcx, [rdi+1D8h]; unsigned __int16 *
0x14003b307  call    ?BlbAppendNonWriterInfoFile@@YAJPEAGPEAU_GUID@@EPEAPEAG@Z; BlbAppendNonWriterInfoFile(ushort *,_GUID *,uchar,ushort * *)
0x14003b30c  test    eax, eax
0x14003b30e  mov     ebx, eax
0x14003b310  js      loc_14003B40E
0x14003b316  lea     rcx, [rbp+arg_10]; unsigned __int16 **
0x14003b31a  call    ?BlbCreateNonWriterXML@@YAJPEAPEAG@Z; BlbCreateNonWriterXML(ushort * *)
0x14003b31f  mov     ebx, eax
0x14003b321  mov     r13, [rbp+arg_10]
0x14003b325  mov     r14, [rbp+pv]
0x14003b329  test    eax, eax
0x14003b32b  js      loc_14003B412
0x14003b331  mov     r9, r13
0x14003b334  mov     r8d, [rdi+150h]
0x14003b33b  mov     rdx, r14
0x14003b33e  mov     rcx, r12
0x14003b341  call    ?BlbSafeDumpFile@@YAJPEBG0W4_BLB_MEDIA_TYPE@@0@Z; BlbSafeDumpFile(ushort const *,ushort const *,_BLB_MEDIA_TYPE,ushort const *)
0x14003b346  mov     ebx, eax
0x14003b348  test    eax, eax
0x14003b34a  js      loc_14003B412
0x14003b350  test    byte ptr [rdi+154h], 80h
0x14003b357  jz      loc_14003B412
0x14003b35d  cmp     [rdi+114h], r15b
0x14003b364  jz      loc_14003B412
0x14003b36a  mov     ecx, 40h ; '@'; Size
0x14003b36f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003b374  mov     [rbp+pv], rax
0x14003b378  xor     ecx, ecx
0x14003b37a  test    rax, rax
0x14003b37d  jz      short loc_14003B38C
0x14003b37f  mov     rcx, rax; this
0x14003b382  call    ??0CBlbFileVerifier@@QEAA@XZ; CBlbFileVerifier::CBlbFileVerifier(void)
0x14003b387  mov     r15, rax
0x14003b38a  jmp     short loc_14003B38F
0x14003b38c  mov     r15, rcx
0x14003b38f  mov     [rbp+pv], r15
0x14003b393  mov     rdx, r12; unsigned __int16 *
0x14003b396  mov     rcx, r15; this
0x14003b399  call    ?Init@CBlbFileVerifier@@QEAAJPEAG@Z; CBlbFileVerifier::Init(ushort *)
0x14003b39e  mov     ebx, eax
0x14003b3a0  test    eax, eax
0x14003b3a2  js      short loc_14003B412
0x14003b3a4  or      r8, 0FFFFFFFFFFFFFFFFh
0x14003b3a8  xor     ebx, ebx
0x14003b3aa  inc     r8
0x14003b3ad  cmp     [r13+r8*2+0], bx
0x14003b3b3  jnz     short loc_14003B3AA
0x14003b3b5  lea     r8, ds:2[r8*2]; unsigned __int64
0x14003b3bd  mov     rdx, r13; void *
0x14003b3c0  mov     rcx, r15; this
0x14003b3c3  call    ?SetChecksumForData@CBlbFileVerifier@@QEAAJPEAX_K@Z; CBlbFileVerifier::SetChecksumForData(void *,unsigned __int64)
0x14003b3c8  mov     ebx, eax
0x14003b3ca  test    eax, eax
0x14003b3cc  js      short loc_14003B412
0x14003b3ce  add     rdi, 308h
0x14003b3d5  mov     r15, [rdi+8]
0x14003b3d9  cmp     r15, [rdi+10h]
0x14003b3dd  jb      short loc_14003B3FA
0x14003b3df  lea     rdx, [r15+1]
0x14003b3e3  mov     rcx, rdi
0x14003b3e6  call    ?GrowBuffer@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(unsigned __int64)
0x14003b3eb  test    al, al
0x14003b3ed  jnz     short loc_14003B3FA
0x14003b3ef  mov     ecx, 8007000Eh; int
0x14003b3f4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14003b3fa  mov     rax, [rdi]
0x14003b3fd  mov     rcx, [rbp+pv]
0x14003b401  mov     [rax+r15*8], rcx
0x14003b405  inc     qword ptr [rdi+8]
0x14003b409  mov     r15, rcx
0x14003b40c  jmp     short loc_14003B412
0x14003b40e  mov     r14, [rbp+pv]
0x14003b412  test    r14, r14
0x14003b415  jz      short loc_14003B420
0x14003b417  mov     rcx, r14; pv
0x14003b41a  call    cs:__imp_CoTaskMemFree
0x14003b420  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b427  lea     r14, WPP_GLOBAL_Control
0x14003b42e  test    rsi, rsi
0x14003b431  jz      short loc_14003B443
0x14003b433  mov     rcx, rsi; pv
0x14003b436  call    cs:__imp_CoTaskMemFree
0x14003b43c  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b443  test    r12, r12
0x14003b446  jz      short loc_14003B458
0x14003b448  mov     rcx, r12; pv
0x14003b44b  call    cs:__imp_CoTaskMemFree
0x14003b451  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b458  mov     rax, [rbp+var_18]
0x14003b45c  test    rax, rax
0x14003b45f  jz      short loc_14003B471
0x14003b461  mov     rcx, rax; pv
0x14003b464  call    cs:__imp_CoTaskMemFree
0x14003b46a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b471  test    ebx, ebx
0x14003b473  jns     short loc_14003B4BD
0x14003b475  test    r15, r15
0x14003b478  jz      short loc_14003B494
0x14003b47a  mov     rax, [r15]
0x14003b47d  mov     edx, 1
0x14003b482  mov     rcx, r15
0x14003b485  mov     rax, [rax]
0x14003b488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b48d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b494  cmp     rcx, r14
0x14003b497  jz      short loc_14003B4BD
0x14003b499  test    byte ptr [rcx+1Ch], 1
0x14003b49d  jz      short loc_14003B4BD
0x14003b49f  cmp     byte ptr [rcx+19h], 2
0x14003b4a3  jb      short loc_14003B4BD
0x14003b4a5  mov     edx, 170h
0x14003b4aa  mov     r9d, ebx
0x14003b4ad  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003b4b4  mov     rcx, [rcx+10h]
0x14003b4b8  call    WPP_SF_d
0x14003b4bd  test    r13, r13
0x14003b4c0  jz      short loc_14003B4CB
0x14003b4c2  mov     rcx, r13; pv
0x14003b4c5  call    cs:__imp_CoTaskMemFree
0x14003b4cb  mov     eax, ebx
0x14003b4cd  add     rsp, 48h
0x14003b4d1  pop     r15
0x14003b4d3  pop     r14
0x14003b4d5  pop     r13
0x14003b4d7  pop     r12
0x14003b4d9  pop     rdi
0x14003b4da  pop     rsi
0x14003b4db  pop     rbx
0x14003b4dc  pop     rbp
0x14003b4dd  retn
```
