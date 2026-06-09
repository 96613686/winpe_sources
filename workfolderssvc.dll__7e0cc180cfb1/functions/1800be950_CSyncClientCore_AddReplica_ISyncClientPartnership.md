# CSyncClientCore::AddReplica(ISyncClientPartnership *)

- ea: `0x1800be950`
- end: `0x1800beed4`
- name: `?AddReplica@CSyncClientCore@@UEAAJPEAUISyncClientPartnership@@@Z`
- size: `1412`
- prototype: `int(CSyncClientCore *__hidden this, struct ISyncClientPartnership *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x180007e10`
- `0x180007f1c`
- `0x180009188`
- `0x180011314`
- `0x18001133c`
- `0x18001137c`
- `0x180021508`
- `0x18003cab8`
- `0x180058d88`
- `0x1800b86ec`
- `0x1800bb948`
- `0x1800be950`
- `0x1800c0af0`
- `0x18013e010`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x1800beb17`
- `KERNEL32!GetFileAttributesW` at `0x1800beb17`
- `SHELL32!__imp_SHCreateDirectory` at `0x1800beaff`
- `SHELL32!__imp_SHCreateDirectory` at `0x1800beaff`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSyncClientCore::AddReplica(CSyncClientCore *this, struct ISyncClientPartnership *a2)
{
  _BYTE *v4; // rax
  char v5; // cl
  __int16 v6; // ax
  signed int NormalizedWin32Path; // ebx
  __int16 v8; // ax
  int v9; // eax
  DWORD FileAttributesW; // eax
  __int16 v11; // ax
  CSyncClientCore *v12; // rcx
  PVOID v13; // rcx
  __int64 v14; // rdx
  int v15; // ecx
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+34h] [rbp-CCh]
  char v19; // [rsp+38h] [rbp-C8h]
  const char *v20; // [rsp+40h] [rbp-C0h]
  __int64 v21; // [rsp+48h] [rbp-B8h]
  PCWSTR pszPath; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+58h] [rbp-A8h] BYREF
  PWSTR FileName; // [rsp+60h] [rbp-A0h] BYREF
  struct IFileSyncReplicaMetadata *v25; // [rsp+68h] [rbp-98h] BYREF
  GUID v26; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v27; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v28[2046]; // [rsp+82h] [rbp-7Eh] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
  }
  if ( (v4[68] & 0x20) != 0 && v4[65] >= 6u )
  {
    v5 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v5 = 0;
LABEL_9:
  v17 = 0;
  v18 = 214;
  v19 = v5;
  v20 = "CSyncClientCore::AddReplica";
  v21 = 0;
  FileName = 0;
  pszPath = 0;
  v25 = 0;
  v6 = 222;
  if ( a2 )
  {
    v17 = 0;
    LOWORD(v18) = 222;
    NormalizedWin32Path = (*(__int64 (__fastcall **)(struct ISyncClientPartnership *, PWSTR *))(*(_QWORD *)a2 + 56LL))(
                            a2,
                            &FileName);
    v17 = NormalizedWin32Path;
    v8 = 224;
    if ( NormalizedWin32Path < 0 )
      goto LABEL_13;
    LOWORD(v18) = 224;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 16, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids, FileName);
    }
    NormalizedWin32Path = CPathUtilities::GetNormalizedWin32Path(FileName, (unsigned __int16 **)&pszPath);
    v17 = NormalizedWin32Path;
    v8 = 229;
    if ( NormalizedWin32Path < 0 )
      goto LABEL_13;
    LOWORD(v18) = 229;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids, pszPath);
    }
    v9 = SHCreateDirectory(0, pszPath);
    NormalizedWin32Path = v9;
    if ( v9 == 183 )
    {
      FileAttributesW = GetFileAttributesW(pszPath);
      if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids, pszPath);
        }
        NormalizedWin32Path = -2147024816;
        v6 = 245;
        goto LABEL_11;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 19, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids, pszPath);
      }
    }
    else
    {
      if ( v9 > 0 )
        NormalizedWin32Path = (unsigned __int16)v9 | 0x80070000;
      v17 = NormalizedWin32Path;
      v8 = 254;
      if ( NormalizedWin32Path < 0 )
        goto LABEL_13;
      LOWORD(v18) = 254;
    }
    v26 = GUID_NULL;
    NormalizedWin32Path = (*(__int64 (__fastcall **)(_QWORD, PCWSTR, GUID *, struct IFileSyncReplicaMetadata **))(**((_QWORD **)this + 69) + 40LL))(
                            *((_QWORD *)this + 69),
                            pszPath,
                            &v26,
                            &v25);
    v6 = 268;
    if ( NormalizedWin32Path >= 0 )
    {
      NormalizedWin32Path = -2147024713;
      goto LABEL_11;
    }
    LOWORD(v18) = 268;
    v8 = 271;
    if ( NormalizedWin32Path != -2147216768 )
    {
      v17 = NormalizedWin32Path;
LABEL_13:
      HIWORD(v18) = v8;
      goto LABEL_63;
    }
    v17 = 0;
    LOWORD(v18) = 271;
    NormalizedWin32Path = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 69) + 152LL))(*((_QWORD *)this + 69));
    v17 = NormalizedWin32Path;
    v8 = 277;
    if ( NormalizedWin32Path < 0 )
      goto LABEL_13;
    LOWORD(v18) = 277;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids, pszPath);
    }
    v17 = (*(__int64 (__fastcall **)(_QWORD, PCWSTR, _QWORD))(**((_QWORD **)this + 69) + 24LL))(
            *((_QWORD *)this + 69),
            pszPath,
            0);
    v11 = 282;
    if ( v17 >= 0 )
    {
      LOWORD(v18) = 282;
      v26 = GUID_NULL;
      v17 = (*(__int64 (__fastcall **)(_QWORD, PCWSTR, GUID *, struct IFileSyncReplicaMetadata **))(**((_QWORD **)this + 69)
                                                                                                  + 40LL))(
              *((_QWORD *)this + 69),
              pszPath,
              &v26,
              &v25);
      v11 = 289;
      if ( v17 >= 0 )
      {
        LOWORD(v18) = 289;
        v23 = 0;
        v17 = (*(__int64 (__fastcall **)(struct IFileSyncReplicaMetadata *, int *))(*(_QWORD *)v25 + 256LL))(v25, &v23);
        v11 = 295;
        if ( v17 >= 0 )
        {
          LOWORD(v18) = 295;
          v11 = 296;
          if ( v23 == 1 )
          {
            LOWORD(v18) = 296;
            v17 = CSyncClientCore::InitializeReplica(v12, pszPath, v25);
            v11 = 303;
            if ( v17 >= 0 )
            {
              LOWORD(v18) = 303;
              v17 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 69) + 168LL))(*((_QWORD *)this + 69));
              v11 = 305;
              if ( v17 >= 0 )
              {
                LOWORD(v18) = 305;
                CSelectiveWipe::ApplyEncryptionPolicy(a2);
                v13 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
                {
                  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids);
                }
                if ( (Microsoft_Windows_WorkFoldersEnableBits & 1) != 0 )
                  McTemplateU0z_EventWriteTransfer(v13, ECSHOST_EVENT_CORESYNC_ADD_REPLICA_SUCCEEDED, FileName);
                goto LABEL_62;
              }
            }
          }
          else
          {
            v17 = -2147418113;
          }
        }
      }
    }
    HIWORD(v18) = v11;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 69) + 160LL))(*((_QWORD *)this + 69));
LABEL_62:
    NormalizedWin32Path = v17;
LABEL_63:
    if ( NormalizedWin32Path > -1 )
      goto LABEL_67;
    goto LABEL_64;
  }
  NormalizedWin32Path = -2147024809;
LABEL_11:
  v17 = NormalizedWin32Path;
  HIWORD(v18) = v6;
LABEL_64:
  if ( FileName && (Microsoft_Windows_WorkFoldersEnableBits & 4) != 0 )
  {
    v27 = 0;
    memset_0(v28, 0, sizeof(v28));
    CEcsFunctionTracer::GetErrorText(NormalizedWin32Path, v14, &v27);
    McTemplateU0zzd_EventWriteTransfer(
      v15,
      (unsigned int)ECSHOST_EVENT_CORESYNC_ADD_REPLICA_FAILED,
      (_DWORD)FileName,
      (unsigned int)&v27,
      NormalizedWin32Path);
    NormalizedWin32Path = v17;
  }
LABEL_67:
  if ( (NormalizedWin32Path & 0x1FFF0000) == 0xE5E0000 )
    NormalizedWin32Path = -2134375657;
  v17 = NormalizedWin32Path;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&pszPath);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v17);
  return (unsigned int)NormalizedWin32Path;
}

```

## disassembly

```asm
0x1800be950  mov     [rsp-8+arg_10], rbx
0x1800be955  mov     [rsp-8+arg_18], rsi
0x1800be95a  push    rbp
0x1800be95b  push    rdi
0x1800be95c  push    r13
0x1800be95e  lea     rbp, [rsp-790h]
0x1800be966  sub     rsp, 890h
0x1800be96d  mov     rax, cs:__security_cookie
0x1800be974  xor     rax, rsp
0x1800be977  mov     [rbp+7A0h+var_20], rax
0x1800be97e  mov     rsi, rdx
0x1800be981  mov     rdi, rcx
0x1800be984  lea     r13, WPP_GLOBAL_Control
0x1800be98b  mov     rax, cs:WPP_GLOBAL_Control
0x1800be992  cmp     rax, r13
0x1800be995  jz      short loc_1800BE9BF
0x1800be997  test    byte ptr [rax+44h], 20h
0x1800be99b  jz      short loc_1800BE9CF
0x1800be99d  cmp     byte ptr [rax+41h], 6
0x1800be9a1  jb      short loc_1800BE9BF
0x1800be9a3  mov     edx, 0Fh
0x1800be9a8  lea     r8, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids
0x1800be9af  mov     rcx, [rax+38h]
0x1800be9b3  call    WPP_SF_
0x1800be9b8  mov     rax, cs:WPP_GLOBAL_Control
0x1800be9bf  test    byte ptr [rax+44h], 20h
0x1800be9c3  jz      short loc_1800BE9CF
0x1800be9c5  cmp     byte ptr [rax+41h], 6
0x1800be9c9  jb      short loc_1800BE9CF
0x1800be9cb  mov     cl, 1
0x1800be9cd  jmp     short loc_1800BE9D1
0x1800be9cf  xor     cl, cl
0x1800be9d1  mov     [rsp+8A0h+var_870], 0
0x1800be9d9  mov     [rsp+8A0h+var_86C], 0D6h
0x1800be9e1  mov     [rsp+8A0h+var_868], cl
0x1800be9e5  lea     rax, aCsyncclientcor_9; "CSyncClientCore::AddReplica"
0x1800be9ec  mov     [rsp+8A0h+var_860], rax
0x1800be9f1  mov     [rsp+8A0h+var_858], 0
0x1800be9fa  mov     [rsp+8A0h+FileName], 0
0x1800bea03  mov     [rsp+8A0h+pszPath], 0
0x1800bea0c  mov     [rsp+8A0h+var_838], 0
0x1800bea15  mov     eax, 0DEh
0x1800bea1a  test    rsi, rsi
0x1800bea1d  jnz     short loc_1800BEA32
0x1800bea1f  mov     ebx, 80070057h
0x1800bea24  mov     [rsp+8A0h+var_870], ebx
0x1800bea28  mov     word ptr [rsp+8A0h+var_86C+2], ax
0x1800bea2d  jmp     loc_1800BEE23
0x1800bea32  mov     [rsp+8A0h+var_870], 0
0x1800bea3a  mov     word ptr [rsp+8A0h+var_86C], ax
0x1800bea3f  mov     rax, [rsi]
0x1800bea42  lea     rdx, [rsp+8A0h+FileName]
0x1800bea47  mov     rcx, rsi
0x1800bea4a  mov     rax, [rax+38h]
0x1800bea4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bea53  mov     ebx, eax
0x1800bea55  mov     [rsp+8A0h+var_870], eax
0x1800bea59  test    eax, eax
0x1800bea5b  mov     eax, 0E0h
0x1800bea60  jns     short loc_1800BEA6C
0x1800bea62  mov     word ptr [rsp+8A0h+var_86C+2], ax
0x1800bea67  jmp     loc_1800BEE1E
0x1800bea6c  mov     word ptr [rsp+8A0h+var_86C], ax
0x1800bea71  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bea78  cmp     rcx, r13
0x1800bea7b  jz      short loc_1800BEAA3
0x1800bea7d  test    byte ptr [rcx+44h], 20h
0x1800bea81  jz      short loc_1800BEAA3
0x1800bea83  cmp     byte ptr [rcx+41h], 4
0x1800bea87  jb      short loc_1800BEAA3
0x1800bea89  mov     edx, 10h
0x1800bea8e  mov     r9, [rsp+8A0h+FileName]
0x1800bea93  lea     r8, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids
0x1800bea9a  mov     rcx, [rcx+38h]
0x1800bea9e  call    WPP_SF_S
0x1800beaa3  lea     rdx, [rsp+8A0h+pszPath]; unsigned __int16 **
0x1800beaa8  mov     rcx, [rsp+8A0h+FileName]; FileName
0x1800beaad  call    ?GetNormalizedWin32Path@CPathUtilities@@SAJPEBGPEAPEAG@Z; CPathUtilities::GetNormalizedWin32Path(ushort const *,ushort * *)
0x1800beab2  mov     ebx, eax
0x1800beab4  mov     [rsp+8A0h+var_870], eax
0x1800beab8  test    eax, eax
0x1800beaba  mov     eax, 0E5h
0x1800beabf  js      short loc_1800BEA62
0x1800beac1  mov     word ptr [rsp+8A0h+var_86C], ax
0x1800beac6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800beacd  cmp     rcx, r13
0x1800bead0  jz      short loc_1800BEAF8
0x1800bead2  test    byte ptr [rcx+44h], 20h
0x1800bead6  jz      short loc_1800BEAF8
0x1800bead8  cmp     byte ptr [rcx+41h], 4
0x1800beadc  jb      short loc_1800BEAF8
0x1800beade  mov     edx, 11h
0x1800beae3  mov     r9, [rsp+8A0h+pszPath]
0x1800beae8  lea     r8, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids
0x1800beaef  mov     rcx, [rcx+38h]
0x1800beaf3  call    WPP_SF_S
0x1800beaf8  mov     rdx, [rsp+8A0h+pszPath]; pszPath
0x1800beafd  xor     ecx, ecx; hwnd
0x1800beaff  call    cs:__imp_SHCreateDirectory
0x1800beb05  mov     ebx, eax
0x1800beb07  cmp     eax, 0B7h
0x1800beb0c  jnz     loc_1800BEBA7
0x1800beb12  mov     rcx, [rsp+8A0h+pszPath]; lpFileName
0x1800beb17  call    cs:__imp_GetFileAttributesW
0x1800beb1d  cmp     eax, 0FFFFFFFFh
0x1800beb20  jz      short loc_1800BEB66
0x1800beb22  test    al, 10h
0x1800beb24  jz      short loc_1800BEB66
0x1800beb26  mov     rcx, cs:WPP_GLOBAL_Control
0x1800beb2d  cmp     rcx, r13
0x1800beb30  jz      loc_1800BEBCA
0x1800beb36  test    byte ptr [rcx+44h], 20h
0x1800beb3a  jz      loc_1800BEBCA
0x1800beb40  cmp     byte ptr [rcx+41h], 4
0x1800beb44  jb      loc_1800BEBCA
0x1800beb4a  mov     edx, 13h
0x1800beb4f  mov     r9, [rsp+8A0h+pszPath]
0x1800beb54  lea     r8, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids
0x1800beb5b  mov     rcx, [rcx+38h]
0x1800beb5f  call    WPP_SF_S
0x1800beb64  jmp     short loc_1800BEBCA
0x1800beb66  mov     rcx, cs:WPP_GLOBAL_Control
0x1800beb6d  cmp     rcx, r13
0x1800beb70  jz      short loc_1800BEB98
0x1800beb72  test    byte ptr [rcx+44h], 20h
0x1800beb76  jz      short loc_1800BEB98
0x1800beb78  cmp     byte ptr [rcx+41h], 4
0x1800beb7c  jb      short loc_1800BEB98
0x1800beb7e  mov     edx, 12h
0x1800beb83  mov     r9, [rsp+8A0h+pszPath]
0x1800beb88  lea     r8, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids
0x1800beb8f  mov     rcx, [rcx+38h]
0x1800beb93  call    WPP_SF_S
0x1800beb98  mov     ebx, 80070050h
0x1800beb9d  mov     eax, 0F5h
0x1800beba2  jmp     loc_1800BEA24
0x1800beba7  test    eax, eax
0x1800beba9  jle     short loc_1800BEBB4
0x1800bebab  movzx   ebx, ax
0x1800bebae  or      ebx, 80070000h
0x1800bebb4  mov     [rsp+8A0h+var_870], ebx
0x1800bebb8  mov     eax, 0FEh
0x1800bebbd  test    ebx, ebx
0x1800bebbf  js      loc_1800BEA62
0x1800bebc5  mov     word ptr [rsp+8A0h+var_86C], ax
0x1800bebca  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800bebd1  movdqu  [rsp+8A0h+var_830], xmm0
0x1800bebd7  mov     rcx, [rdi+228h]
0x1800bebde  mov     rax, [rcx]
0x1800bebe1  lea     r9, [rsp+8A0h+var_838]
0x1800bebe6  lea     r8, [rsp+8A0h+var_830]
0x1800bebeb  mov     rdx, [rsp+8A0h+pszPath]
0x1800bebf0  mov     rax, [rax+28h]
0x1800bebf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bebf9  mov     ebx, eax
0x1800bebfb  test    eax, eax
0x1800bebfd  mov     eax, 10Ch
0x1800bec02  js      short loc_1800BEC0E
0x1800bec04  mov     ebx, 800700B7h
0x1800bec09  jmp     loc_1800BEA24
0x1800bec0e  mov     word ptr [rsp+8A0h+var_86C], ax
0x1800bec13  mov     eax, 10Fh
0x1800bec18  cmp     ebx, 80041280h
0x1800bec1e  jz      short loc_1800BEC29
0x1800bec20  mov     [rsp+8A0h+var_870], ebx
0x1800bec24  jmp     loc_1800BEA62
0x1800bec29  mov     [rsp+8A0h+var_870], 0
0x1800bec31  mov     word ptr [rsp+8A0h+var_86C], ax
0x1800bec36  mov     rcx, [rdi+228h]
0x1800bec3d  mov     rax, [rcx]
0x1800bec40  mov     rax, [rax+98h]
0x1800bec47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bec4c  mov     ebx, eax
0x1800bec4e  mov     [rsp+8A0h+var_870], eax
0x1800bec52  test    eax, eax
0x1800bec54  mov     eax, 115h
0x1800bec59  js      loc_1800BEA62
0x1800bec5f  mov     word ptr [rsp+8A0h+var_86C], ax
0x1800bec64  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bec6b  cmp     rcx, r13
0x1800bec6e  jz      short loc_1800BEC96
0x1800bec70  test    byte ptr [rcx+44h], 20h
0x1800bec74  jz      short loc_1800BEC96
0x1800bec76  cmp     byte ptr [rcx+41h], 4
0x1800bec7a  jb      short loc_1800BEC96
0x1800bec7c  mov     edx, 14h
0x1800bec81  mov     r9, [rsp+8A0h+pszPath]
0x1800bec86  lea     r8, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids
0x1800bec8d  mov     rcx, [rcx+38h]
0x1800bec91  call    WPP_SF_S
0x1800bec96  mov     rcx, [rdi+228h]
0x1800bec9d  mov     rax, [rcx]
0x1800beca0  xor     r8d, r8d
0x1800beca3  mov     rdx, [rsp+8A0h+pszPath]
0x1800beca8  mov     rax, [rax+18h]
0x1800becac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800becb1  mov     [rsp+8A0h+var_870], eax
0x1800becb5  test    eax, eax
0x1800becb7  mov     eax, 11Ah
0x1800becbc  js      loc_1800BEDA6
0x1800becc2  mov     word ptr [rsp+8A0h+var_86C], ax
0x1800becc7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800becce  movdqu  [rsp+8A0h+var_830], xmm0
0x1800becd4  mov     rcx, [rdi+228h]
0x1800becdb  mov     rax, [rcx]
0x1800becde  lea     r9, [rsp+8A0h+var_838]
0x1800bece3  lea     r8, [rsp+8A0h+var_830]
0x1800bece8  mov     rdx, [rsp+8A0h+pszPath]
0x1800beced  mov     rax, [rax+28h]
0x1800becf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800becf6  mov     [rsp+8A0h+var_870], eax
0x1800becfa  test    eax, eax
0x1800becfc  mov     eax, 121h
0x1800bed01  js      loc_1800BEDA6
0x1800bed07  mov     word ptr [rsp+8A0h+var_86C], ax
0x1800bed0c  mov     [rsp+8A0h+var_848], 0
0x1800bed14  mov     rcx, [rsp+8A0h+var_838]
0x1800bed19  mov     rax, [rcx]
0x1800bed1c  lea     rdx, [rsp+8A0h+var_848]
0x1800bed21  mov     rax, [rax+100h]
0x1800bed28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bed2d  mov     [rsp+8A0h+var_870], eax
0x1800bed31  test    eax, eax
0x1800bed33  mov     eax, 127h
0x1800bed38  js      short loc_1800BEDA6
0x1800bed3a  mov     word ptr [rsp+8A0h+var_86C], ax
0x1800bed3f  mov     eax, 128h
0x1800bed44  cmp     [rsp+8A0h+var_848], 1
0x1800bed49  jz      short loc_1800BED55
0x1800bed4b  mov     [rsp+8A0h+var_870], 8000FFFFh
0x1800bed53  jmp     short loc_1800BEDA6
0x1800bed55  mov     [rsp+8A0h+var_870], 0
0x1800bed5d  mov     word ptr [rsp+8A0h+var_86C], ax
0x1800bed62  mov     r8, [rsp+8A0h+var_838]; struct IFileSyncReplicaMetadata *
0x1800bed67  mov     rdx, [rsp+8A0h+pszPath]; unsigned __int16 *
0x1800bed6c  call    ?InitializeReplica@CSyncClientCore@@AEAAJPEBGPEAUIFileSyncReplicaMetadata@@@Z; CSyncClientCore::InitializeReplica(ushort const *,IFileSyncReplicaMetadata *)
0x1800bed71  mov     [rsp+8A0h+var_870], eax
0x1800bed75  test    eax, eax
0x1800bed77  mov     eax, 12Fh
0x1800bed7c  js      short loc_1800BEDA6
0x1800bed7e  mov     word ptr [rsp+8A0h+var_86C], ax
0x1800bed83  mov     rcx, [rdi+228h]
0x1800bed8a  mov     rax, [rcx]
0x1800bed8d  mov     rax, [rax+0A8h]
0x1800bed94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bed99  mov     [rsp+8A0h+var_870], eax
0x1800bed9d  test    eax, eax
0x1800bed9f  mov     eax, 131h
0x1800beda4  jns     short loc_1800BEDC3
0x1800beda6  mov     word ptr [rsp+8A0h+var_86C+2], ax
0x1800bedab  mov     rcx, [rdi+228h]
0x1800bedb2  mov     rax, [rcx]
0x1800bedb5  mov     rax, [rax+0A0h]
0x1800bedbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bedc1  jmp     short loc_1800BEE1A
0x1800bedc3  mov     word ptr [rsp+8A0h+var_86C], ax
0x1800bedc8  mov     rcx, rsi; struct ISyncClientPartnership *
0x1800bedcb  call    ?ApplyEncryptionPolicy@CSelectiveWipe@@SAJPEAUISyncClientPartnership@@@Z; CSelectiveWipe::ApplyEncryptionPolicy(ISyncClientPartnership *)
0x1800bedd0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bedd7  cmp     rcx, r13
0x1800bedda  jz      short loc_1800BEE00
0x1800beddc  test    byte ptr [rcx+44h], 20h
0x1800bede0  jz      short loc_1800BEE00
0x1800bede2  cmp     byte ptr [rcx+41h], 4
0x1800bede6  jb      short loc_1800BEE00
0x1800bede8  mov     edx, 15h
0x1800beded  mov     r9d, eax
0x1800bedf0  lea     r8, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids
0x1800bedf7  mov     rcx, [rcx+38h]
0x1800bedfb  call    WPP_SF_d
0x1800bee00  test    byte ptr cs:Microsoft_Windows_WorkFoldersEnableBits, 1
0x1800bee07  jz      short loc_1800BEE1A
0x1800bee09  mov     r8, [rsp+8A0h+FileName]
0x1800bee0e  lea     rdx, ECSHOST_EVENT_CORESYNC_ADD_REPLICA_SUCCEEDED
0x1800bee15  call    McTemplateU0z_EventWriteTransfer
0x1800bee1a  mov     ebx, [rsp+8A0h+var_870]
0x1800bee1e  cmp     ebx, 0FFFFFFFFh
0x1800bee21  jg      short loc_1800BEE73
0x1800bee23  cmp     [rsp+8A0h+FileName], 0
0x1800bee29  jz      short loc_1800BEE73
0x1800bee2b  test    byte ptr cs:Microsoft_Windows_WorkFoldersEnableBits, 4
0x1800bee32  jz      short loc_1800BEE73
0x1800bee34  xor     eax, eax
0x1800bee36  mov     [rbp+7A0h+var_820], ax
0x1800bee3a  xor     edx, edx; Val
0x1800bee3c  mov     r8d, 7FEh; Size
0x1800bee42  lea     rcx, [rbp+7A0h+var_81E]; void *
0x1800bee46  call    memset_0
0x1800bee4b  lea     r8, [rbp+7A0h+var_820]; unsigned __int16 *
0x1800bee4f  mov     ecx, ebx; dwMessageId
0x1800bee51  call    ?GetErrorText@CEcsFunctionTracer@@SAXJ_KPEAG@Z; CEcsFunctionTracer::GetErrorText(long,unsigned __int64,ushort *)
0x1800bee56  mov     [rsp+8A0h+var_880], ebx
0x1800bee5a  lea     r9, [rbp+7A0h+var_820]
0x1800bee5e  mov     r8, [rsp+8A0h+FileName]
0x1800bee63  lea     rdx, ECSHOST_EVENT_CORESYNC_ADD_REPLICA_FAILED
0x1800bee6a  call    McTemplateU0zzd_EventWriteTransfer
0x1800bee6f  mov     ebx, [rsp+8A0h+var_870]
0x1800bee73  mov     ecx, ebx
0x1800bee75  and     ecx, 1FFF0000h
0x1800bee7b  mov     eax, 80C80317h
  ... truncated ...
```
