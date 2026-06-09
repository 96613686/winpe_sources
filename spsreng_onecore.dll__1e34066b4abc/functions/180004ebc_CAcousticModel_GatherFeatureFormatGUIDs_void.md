# CAcousticModel::GatherFeatureFormatGUIDs(void)

- ea: `0x180004ebc`
- end: `0x1800052e7`
- name: `?GatherFeatureFormatGUIDs@CAcousticModel@@QEAAJXZ`
- size: `1067`
- prototype: `__int64 __fastcall(CAcousticModel *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800055f8`

## callees

- `0x180002470`
- `0x180002db8`
- `0x1800034b0`
- `0x1800040b8`
- `0x180004adc`
- `0x180004ebc`
- `0x1800055cc`
- `0x180005eb8`
- `0x1800060c0`
- `0x1800061d0`
- `0x180020cec`
- `0x1800ff514`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004ff7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800051dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005208`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004ff7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800051dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005208`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005145`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005145`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180005022`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180005022`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000504a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000504a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800051e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005224`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800051e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005224`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAcousticModel::GatherFeatureFormatGUIDs(CFeatureFormat **this)
{
  unsigned int v2; // edx
  int Win32Error; // ebx
  unsigned int i; // r14d
  int v5; // eax
  CAcousticModel *v6; // rcx
  HANDLE FileW; // rax
  void *v8; // r15
  struct tWAVEFORMATEX *v9; // rsi
  CFeatureFormat *v10; // rdx
  CFeatureFormat *j; // r8
  __int64 v12; // rcx
  char *v13; // rax
  char v15; // r9
  CFeatureFormat *v16; // r8
  CFeatureFormat *v17; // rdx
  CFeatureFormat *v18; // rcx
  unsigned __int16 *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v20; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v22; // [rsp+4Ch] [rbp-B4h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+58h] [rbp-A8h] BYREF
  int v25; // [rsp+60h] [rbp-A0h] BYREF
  int v26; // [rsp+64h] [rbp-9Ch] BYREF
  char *v27; // [rsp+68h] [rbp-98h]
  struct _GUID v28; // [rsp+70h] [rbp-90h] BYREF
  _BYTE Buffer[80]; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID v30; // [rsp+D0h] [rbp-30h]
  WCHAR FileName[264]; // [rsp+E0h] [rbp-20h] BYREF

  v24 = 0;
  v25 = 0;
  v26 = 0;
  v22 = 0;
  NumberOfBytesRead = 0;
  memset_0(Buffer, 0, 0x60u);
  pv = 0;
  v28 = 0;
  if ( *this )
    CFeatureFormat::`scalar deleting destructor'(*this, v2);
  *this = 0;
  Win32Error = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 *))(**((_QWORD **)this[1] + 33) + 72LL))(
                 *((_QWORD *)this[1] + 33),
                 L"AMs",
                 &v24);
  if ( Win32Error >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      v20 = 0;
      v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 **))(*(_QWORD *)v24 + 112LL))(v24, i, &v20);
      Win32Error = v5;
      if ( v5 )
        break;
      if ( (unsigned int)CAcousticModel::ParseAMName(
                           v6,
                           v20,
                           (enum MSAM_AGE *)&v26,
                           (enum MSAM_GENDER *)&v25,
                           &v22,
                           dwFlagsAndAttributes) )
      {
        pv = 0;
        (*(void (__fastcall **)(__int64, unsigned __int16 *, LPVOID *))(*(_QWORD *)v24 + 48LL))(v24, v20, &pv);
        StringCchPrintfW(FileName, 0x105u, L"%s.am", pv);
        CoTaskMemFree(pv);
        FileW = CreateFileW(FileName, 0x80000000, Win32Error + 1, 0, 3u, 0x80u, 0);
        v8 = FileW;
        if ( FileW == (HANDLE)-1LL )
        {
          Win32Error = HrFromLastWin32Error();
LABEL_34:
          CSpDynamicString::_free((CSpDynamicString *)&v20);
          goto LABEL_35;
        }
        if ( !ReadFile(FileW, Buffer, Win32Error + 96, &NumberOfBytesRead, 0) || NumberOfBytesRead != 96 )
        {
          Win32Error = HrFromLastWin32Error();
          goto LABEL_32;
        }
        if ( !memcmp_0(Buffer, &ACOUSTICMODELMAGIC_6, (unsigned int)(Win32Error + 16)) )
        {
          v28 = v30;
        }
        else
        {
          if ( memcmp_0(Buffer, &ACOUSTICMODELMAGIC_5, 0x10u) )
            goto LABEL_29;
          if ( v22 == 3 )
          {
            v28.Data1 = 419851976;
            *(_DWORD *)&v28.Data2 = 1114387628;
            *(_DWORD *)v28.Data4 = 26509200;
            *(_DWORD *)&v28.Data4[4] = 1613545838;
          }
          else
          {
            if ( v22 != 4 )
            {
LABEL_29:
              Win32Error = 1;
LABEL_32:
              CSpDynamicString::_free((CSpDynamicString *)&v20);
              CloseHandle(v8);
              goto LABEL_35;
            }
            v28.Data1 = -1084493010;
            *(_DWORD *)&v28.Data2 = -970043848;
            *(_DWORD *)v28.Data4 = 1041489071;
            *(_DWORD *)&v28.Data4[4] = -533107720;
          }
        }
        v9 = (struct tWAVEFORMATEX *)CoTaskMemAlloc(0x12u);
        Win32Error = CFEManager::GetPreferredWaveFormatEx((CFEManager *)CFEManager::s_pFEManager, &v28, v9);
        if ( Win32Error < 0 )
        {
          CoTaskMemFree(v9);
          goto LABEL_32;
        }
        v10 = *this;
        for ( j = *this; j; j = *(CFeatureFormat **)j )
        {
          v12 = *((_QWORD *)v10 + 1) - *(_QWORD *)&v28.Data1;
          if ( !v12 )
            v12 = *((_QWORD *)v10 + 2) - *(_QWORD *)v28.Data4;
          if ( !v12 || *((_DWORD *)v10 + 6) == v9->nSamplesPerSec )
            goto LABEL_27;
        }
        v13 = (char *)CWinHeap::Alloc((CWinHeap *)&g_heap, 0x20u, 0);
        v27 = v13;
        if ( v13 )
        {
          *(_QWORD *)v13 = *this;
          *(struct _GUID *)(v13 + 8) = v28;
          *((_DWORD *)v13 + 6) = v9->nSamplesPerSec;
          *this = (CFeatureFormat *)v13;
        }
LABEL_27:
        CoTaskMemFree(v9);
        CloseHandle(v8);
      }
      CSpDynamicString::_free((CSpDynamicString *)&v20);
    }
    if ( v5 != -2147200967 )
      goto LABEL_34;
    Win32Error = 0;
    CSpDynamicString::_free((CSpDynamicString *)&v20);
    if ( *this && *(_QWORD *)*this )
    {
      do
      {
        v15 = 1;
        v16 = 0;
        v17 = *this;
        v18 = *(CFeatureFormat **)*this;
        if ( !v18 )
          break;
        do
        {
          if ( *((_DWORD *)v17 + 6) < *((_DWORD *)v18 + 6) )
          {
            v15 = 0;
            *(_QWORD *)v17 = *(_QWORD *)v18;
            *(_QWORD *)v18 = v17;
            if ( v16 )
              *(_QWORD *)v16 = v18;
            else
              *this = v18;
            v17 = v18;
            v18 = *(CFeatureFormat **)v18;
          }
          v16 = v17;
          v17 = v18;
          v18 = *(CFeatureFormat **)v18;
        }
        while ( v18 );
      }
      while ( !v15 );
    }
  }
LABEL_35:
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v24);
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x180004ebc  mov     [rsp-8+arg_8], rbx
0x180004ec1  mov     [rsp-8+arg_10], rsi
0x180004ec6  push    rbp
0x180004ec7  push    rdi
0x180004ec8  push    r12
0x180004eca  push    r14
0x180004ecc  push    r15
0x180004ece  lea     rbp, [rsp-200h]
0x180004ed6  sub     rsp, 300h
0x180004edd  mov     rax, cs:__security_cookie
0x180004ee4  xor     rax, rsp
0x180004ee7  mov     [rbp+220h+var_30], rax
0x180004eee  mov     rdi, rcx
0x180004ef1  xor     r12d, r12d
0x180004ef4  mov     [rsp+320h+var_2C8], r12
0x180004ef9  mov     [rsp+320h+var_2C0], r12d
0x180004efe  mov     [rsp+320h+var_2BC], r12d
0x180004f03  mov     [rsp+320h+var_2D4], r12d
0x180004f08  mov     [rsp+320h+NumberOfBytesRead], r12d
0x180004f0d  xor     edx, edx; Val
0x180004f0f  lea     r8d, [r12+60h]; Size
0x180004f14  lea     rcx, [rbp+220h+Buffer]; void *
0x180004f18  call    memset_0
0x180004f1d  mov     [rsp+320h+pv], r12
0x180004f22  xorps   xmm0, xmm0
0x180004f25  movups  xmmword ptr [rsp+320h+var_2B0.Data1], xmm0
0x180004f2a  mov     rcx, [rdi]; this
0x180004f2d  test    rcx, rcx
0x180004f30  jz      short loc_180004F37
0x180004f32  call    ??_GCFeatureFormat@@QEAAPEAXI@Z; CFeatureFormat::`scalar deleting destructor'(uint)
0x180004f37  mov     [rdi], r12
0x180004f3a  mov     rax, [rdi+8]
0x180004f3e  mov     rcx, [rax+108h]
0x180004f45  mov     rax, [rcx]
0x180004f48  lea     r8, [rsp+320h+var_2C8]
0x180004f4d  lea     rdx, aAms; "AMs"
0x180004f54  mov     rax, [rax+48h]
0x180004f58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f5d  mov     ebx, eax
0x180004f5f  test    eax, eax
0x180004f61  js      loc_18000523E
0x180004f67  mov     r14d, r12d
0x180004f6a  mov     [rsp+320h+var_2E0], r12
0x180004f6f  mov     rcx, [rsp+320h+var_2C8]
0x180004f74  mov     rax, [rcx]
0x180004f77  lea     r8, [rsp+320h+var_2E0]
0x180004f7c  mov     edx, r14d
0x180004f7f  mov     rax, [rax+70h]
0x180004f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f88  mov     ebx, eax
0x180004f8a  test    eax, eax
0x180004f8c  jnz     loc_180005275
0x180004f92  lea     rax, [rsp+320h+var_2D4]
0x180004f97  mov     qword ptr [rsp+320h+dwCreationDisposition], rax; unsigned int *
0x180004f9c  lea     r9, [rsp+320h+var_2C0]; enum MSAM_GENDER *
0x180004fa1  lea     r8, [rsp+320h+var_2BC]; enum MSAM_AGE *
0x180004fa6  mov     rdx, [rsp+320h+var_2E0]; unsigned __int16 *
0x180004fab  call    ?ParseAMName@CAcousticModel@@AEAAHPEBGPEAW4MSAM_AGE@@PEAW4MSAM_GENDER@@PEAKPEAG@Z; CAcousticModel::ParseAMName(ushort const *,MSAM_AGE *,MSAM_GENDER *,ulong *,ushort *)
0x180004fb0  test    eax, eax
0x180004fb2  jz      loc_1800051EC
0x180004fb8  mov     [rsp+320h+pv], r12
0x180004fbd  mov     rcx, [rsp+320h+var_2C8]
0x180004fc2  mov     rax, [rcx]
0x180004fc5  lea     r8, [rsp+320h+pv]
0x180004fca  mov     rdx, [rsp+320h+var_2E0]
0x180004fcf  mov     rax, [rax+30h]
0x180004fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fd8  mov     r9, [rsp+320h+pv]
0x180004fdd  lea     r8, aSAm; "%s.am"
0x180004fe4  mov     edx, 105h; unsigned __int64
0x180004fe9  lea     rcx, [rbp+220h+FileName]; unsigned __int16 *
0x180004fed  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004ff2  mov     rcx, [rsp+320h+pv]; pv
0x180004ff7  call    cs:__imp_CoTaskMemFree
0x180004ffd  mov     [rsp+320h+hTemplateFile], r12; hTemplateFile
0x180005002  mov     dword ptr [rsp+320h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000500a  mov     [rsp+320h+dwCreationDisposition], 3; dwCreationDisposition
0x180005012  xor     r9d, r9d; lpSecurityAttributes
0x180005015  mov     edx, 80000000h; dwDesiredAccess
0x18000501a  lea     r8d, [rbx+1]; dwShareMode
0x18000501e  lea     rcx, [rbp+220h+FileName]; lpFileName
0x180005022  call    cs:__imp_CreateFileW
0x180005028  mov     r15, rax
0x18000502b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000502f  jz      loc_18000522C
0x180005035  mov     qword ptr [rsp+320h+dwCreationDisposition], r12; lpOverlapped
0x18000503a  lea     r9, [rsp+320h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000503f  lea     r8d, [rbx+60h]; nNumberOfBytesToRead
0x180005043  lea     rdx, [rbp+220h+Buffer]; lpBuffer
0x180005047  mov     rcx, rax; hFile
0x18000504a  call    cs:__imp_ReadFile
0x180005050  test    eax, eax
0x180005052  jz      loc_180005210
0x180005058  cmp     [rsp+320h+NumberOfBytesRead], 60h ; '`'
0x18000505d  jnz     loc_180005210
0x180005063  lea     r8d, [rbx+10h]; Size
0x180005067  lea     rdx, ACOUSTICMODELMAGIC_6; Buf2
0x18000506e  lea     rcx, [rbp+220h+Buffer]; Buf1
0x180005072  call    memcmp_0
0x180005077  test    eax, eax
0x180005079  jnz     short loc_1800050CE
0x18000507b  mov     eax, [rbp+220h+var_250]
0x18000507e  mov     [rsp+320h+var_2B0.Data1], eax
0x180005082  movzx   eax, [rbp+220h+var_24C]
0x180005086  mov     [rsp+320h+var_2B0.Data2], ax
0x18000508b  movzx   eax, [rbp+220h+var_24A]
0x18000508f  mov     [rsp+320h+var_2B0.Data3], ax
0x180005094  mov     al, [rbp+220h+var_248]
0x180005097  mov     [rsp+320h+var_2B0.Data4], al
0x18000509b  mov     al, [rbp+220h+var_247]
0x18000509e  mov     [rsp+320h+var_2B0.Data4+1], al
0x1800050a2  mov     al, [rbp+220h+var_246]
0x1800050a5  mov     [rsp+320h+var_2B0.Data4+2], al
0x1800050a9  mov     al, [rbp+220h+var_245]
0x1800050ac  mov     [rsp+320h+var_2B0.Data4+3], al
0x1800050b0  mov     al, [rbp+220h+var_244]
0x1800050b3  mov     [rsp+320h+var_2B0.Data4+4], al
0x1800050b7  mov     al, [rbp+220h+var_243]
0x1800050ba  mov     [rsp+320h+var_2B0.Data4+5], al
0x1800050be  mov     al, [rbp+220h+var_242]
0x1800050c1  mov     [rsp+320h+var_2B0.Data4+6], al
0x1800050c5  mov     al, [rbp+220h+var_241]
0x1800050c8  mov     [rsp+320h+var_2B0.Data4+7], al
0x1800050cc  jmp     short loc_180005140
0x1800050ce  mov     r8d, 10h; Size
0x1800050d4  lea     rdx, ACOUSTICMODELMAGIC_5; Buf2
0x1800050db  lea     rcx, [rbp+220h+Buffer]; Buf1
0x1800050df  call    memcmp_0
0x1800050e4  test    eax, eax
0x1800050e6  jnz     loc_1800051FE
0x1800050ec  mov     eax, [rsp+320h+var_2D4]
0x1800050f0  sub     eax, 3
0x1800050f3  jz      short loc_180005120
0x1800050f5  cmp     eax, 1
0x1800050f8  jnz     loc_1800051FE
0x1800050fe  mov     [rsp+320h+var_2B0.Data1], 0BF5BF32Eh
0x180005106  mov     dword ptr [rsp+320h+var_2B0.Data2], 0C62E4E38h
0x18000510e  mov     dword ptr [rsp+320h+var_2B0.Data4], 3E13DCAFh
0x180005116  mov     dword ptr [rsp+320h+var_2B0.Data4+4], 0E0396BF8h
0x18000511e  jmp     short loc_180005140
0x180005120  mov     [rsp+320h+var_2B0.Data1], 19066EC8h
0x180005128  mov     dword ptr [rsp+320h+var_2B0.Data2], 426C34ACh
0x180005130  mov     dword ptr [rsp+320h+var_2B0.Data4], 1947F90h
0x180005138  mov     dword ptr [rsp+320h+var_2B0.Data4+4], 602CC16Eh
0x180005140  mov     ecx, 12h; cb
0x180005145  call    cs:__imp_CoTaskMemAlloc
0x18000514b  mov     rsi, rax
0x18000514e  mov     r8, rax; struct tWAVEFORMATEX *
0x180005151  lea     rdx, [rsp+320h+var_2B0]; struct _GUID *
0x180005156  mov     rcx, cs:?s_pFEManager@CFEManager@@0PEAV1@EA; this
0x18000515d  call    ?GetPreferredWaveFormatEx@CFEManager@@QEAAJPEBU_GUID@@PEAUtWAVEFORMATEX@@@Z; CFEManager::GetPreferredWaveFormatEx(_GUID const *,tWAVEFORMATEX *)
0x180005162  mov     ebx, eax
0x180005164  test    eax, eax
0x180005166  js      loc_180005205
0x18000516c  mov     rdx, [rdi]
0x18000516f  mov     r8, rdx; bool
0x180005172  test    r8, r8
0x180005175  jz      short loc_1800051A5
0x180005177  mov     rcx, [rdx+8]
0x18000517b  sub     rcx, qword ptr [rsp+320h+var_2B0.Data1]
0x180005180  jnz     short loc_18000518B
0x180005182  mov     rcx, [rdx+10h]
0x180005186  sub     rcx, qword ptr [rsp+320h+var_2B0.Data4]
0x18000518b  mov     eax, r12d
0x18000518e  test    rcx, rcx
0x180005191  setz    al
0x180005194  test    eax, eax
0x180005196  jnz     short loc_1800051D9
0x180005198  mov     eax, [rsi+4]
0x18000519b  cmp     [rdx+18h], eax
0x18000519e  jz      short loc_1800051D9
0x1800051a0  mov     r8, [r8]
0x1800051a3  jmp     short loc_180005172
0x1800051a5  mov     edx, 20h ; ' '; unsigned __int64
0x1800051aa  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800051b1  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x1800051b6  mov     [rsp+320h+var_2B8], rax
0x1800051bb  test    rax, rax
0x1800051be  jz      short loc_1800051D9
0x1800051c0  mov     rcx, [rdi]
0x1800051c3  mov     [rax], rcx
0x1800051c6  movups  xmm0, xmmword ptr [rsp+320h+var_2B0.Data1]
0x1800051cb  movdqu  xmmword ptr [rax+8], xmm0
0x1800051d0  mov     ecx, [rsi+4]
0x1800051d3  mov     [rax+18h], ecx
0x1800051d6  mov     [rdi], rax
0x1800051d9  mov     rcx, rsi; pv
0x1800051dc  call    cs:__imp_CoTaskMemFree
0x1800051e2  mov     rcx, r15; hObject
0x1800051e5  call    cs:__imp_CloseHandle
0x1800051eb  nop
0x1800051ec  lea     rcx, [rsp+320h+var_2E0]; this
0x1800051f1  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x1800051f6  inc     r14d
0x1800051f9  jmp     loc_180004F6A
0x1800051fe  mov     ebx, 1
0x180005203  jmp     short loc_180005217
0x180005205  mov     rcx, rsi; pv
0x180005208  call    cs:__imp_CoTaskMemFree
0x18000520e  jmp     short loc_180005217
0x180005210  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180005215  mov     ebx, eax
0x180005217  lea     rcx, [rsp+320h+var_2E0]; this
0x18000521c  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x180005221  mov     rcx, r15; hObject
0x180005224  call    cs:__imp_CloseHandle
0x18000522a  jmp     short loc_18000523E
0x18000522c  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180005231  mov     ebx, eax
0x180005233  lea     rcx, [rsp+320h+var_2E0]; this
0x180005238  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x18000523d  nop
0x18000523e  lea     rcx, [rsp+320h+var_2C8]
0x180005243  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x180005248  mov     eax, ebx
0x18000524a  mov     rcx, [rbp+220h+var_30]
0x180005251  xor     rcx, rsp; StackCookie
0x180005254  call    __security_check_cookie
0x180005259  lea     r11, [rsp+320h+var_20]
0x180005261  mov     rbx, [r11+38h]
0x180005265  mov     rsi, [r11+40h]
0x180005269  mov     rsp, r11
0x18000526c  pop     r15
0x18000526e  pop     r14
0x180005270  pop     r12
0x180005272  pop     rdi
0x180005273  pop     rbp
0x180005274  retn
0x180005275  cmp     eax, 80045039h
0x18000527a  jnz     short loc_180005233
0x18000527c  mov     ebx, r12d
0x18000527f  lea     rcx, [rsp+320h+var_2E0]; this
0x180005284  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x180005289  mov     rax, [rdi]
0x18000528c  test    rax, rax
0x18000528f  jz      short loc_18000523E
0x180005291  cmp     [rax], r12
0x180005294  jz      short loc_18000523E
0x180005296  mov     r9b, 1
0x180005299  mov     r8, r12
0x18000529c  mov     rdx, [rdi]
0x18000529f  mov     rcx, [rdx]
0x1800052a2  test    rcx, rcx
0x1800052a5  jz      short loc_18000523E
0x1800052a7  mov     eax, [rcx+18h]
0x1800052aa  cmp     [rdx+18h], eax
0x1800052ad  jge     short loc_1800052CE
0x1800052af  mov     r9b, r12b
0x1800052b2  mov     rax, [rcx]
0x1800052b5  mov     [rdx], rax
0x1800052b8  mov     [rcx], rdx
0x1800052bb  test    r8, r8
0x1800052be  jz      short loc_1800052C5
0x1800052c0  mov     [r8], rcx
0x1800052c3  jmp     short loc_1800052C8
0x1800052c5  mov     [rdi], rcx
0x1800052c8  mov     rdx, rcx
0x1800052cb  mov     rcx, [rcx]
0x1800052ce  mov     r8, rdx
0x1800052d1  mov     rdx, rcx
0x1800052d4  mov     rcx, [rcx]
0x1800052d7  test    rcx, rcx
0x1800052da  jnz     short loc_1800052A7
0x1800052dc  test    r9b, r9b
0x1800052df  jz      short loc_180005296
0x1800052e1  jmp     loc_18000523E
```
