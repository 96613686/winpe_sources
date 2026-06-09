# CNtfsFileSystemApplier::UpdateInPlace(IFspFile *,IFspInPlaceFile *,ushort const *,ushort const *,ulong,ulong,void *,ulong,IFileConcurrencyBlob * *)

- ea: `0x18011038c`
- end: `0x18011077c`
- name: `?UpdateInPlace@CNtfsFileSystemApplier@@AEAAJPEAUIFspFile@@PEAUIFspInPlaceFile@@PEBG2KKPEAXKPEAPEAUIFileConcurrencyBlob@@@Z`
- size: `1008`
- prototype: `int(CNtfsFileSystemApplier *__hidden this, struct IFspFile *, struct IFspInPlaceFile *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, void *, unsigned int, struct IFileConcurrencyBlob **)`
- caller_count: `4`
- callee_count: `15`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18010f360`
- `0x18010f5a0`
- `0x18010fa70`
- `0x18010fd2c`

## callees

- `0x180007e10`
- `0x180008080`
- `0x180011314`
- `0x18002db48`
- `0x180058d88`
- `0x1800bb594`
- `0x1800bb748`
- `0x18010c520`
- `0x18011038c`
- `0x180110784`
- `0x180111f4c`
- `0x1801124dc`
- `0x180112bc0`
- `0x180112e84`
- `0x18013e010`

## import_xrefs

- `ntdll!NtSetSecurityObject` at `0x180110671`
- `ntdll!NtSetSecurityObject` at `0x180110671`
- `ntdll!NtClose` at `0x180110733`
- `ntdll!NtClose` at `0x180110733`

## string_xrefs

- `0x180110420`: `CNtfsFileSystemApplier::UpdateInPlace`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CNtfsFileSystemApplier::UpdateInPlace(
        const unsigned __int16 **this,
        struct IFspFile *a2,
        struct IFspInPlaceFile *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned int a7,
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        SECURITY_INFORMATION SecurityInformation,
        struct IFileConcurrencyBlob **a10)
{
  _DWORD *v14; // rax
  char v15; // cl
  struct IFileConcurrencyBlob **v16; // r13
  int NormalizedNtPath; // ebx
  bool v18; // sf
  __int16 v19; // ax
  bool v20; // sf
  const WCHAR *v21; // rdi
  void *v22; // r12
  int v23; // r14d
  unsigned int v24; // r8d
  unsigned int v25; // esi
  ACCESS_MASK v26; // edx
  CNtfsFileSystemApplier *v27; // rcx
  unsigned int v28; // eax
  char *v29; // r8
  int v30; // ecx
  int v31; // eax
  unsigned int v33; // [rsp+28h] [rbp-58h]
  unsigned int v34; // [rsp+40h] [rbp-40h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int16 *Src; // [rsp+50h] [rbp-30h] BYREF
  PCWSTR SourceString; // [rsp+58h] [rbp-28h] BYREF
  int v38; // [rsp+60h] [rbp-20h] BYREF
  int v39; // [rsp+64h] [rbp-1Ch]
  char v40; // [rsp+68h] [rbp-18h]
  const char *v41; // [rsp+70h] [rbp-10h]
  __int64 v42; // [rsp+78h] [rbp-8h]

  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 25, WPP_bfe3f9d07e6736223889f9787b891edb_Traceguids);
      v14 = WPP_GLOBAL_Control;
    }
  }
  if ( (v14[17] & 0x100) != 0 && *((_BYTE *)v14 + 65) >= 6u )
  {
    v15 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v15 = 0;
LABEL_9:
  v38 = 0;
  v39 = 1270;
  v40 = v15;
  v41 = "CNtfsFileSystemApplier::UpdateInPlace";
  v42 = 0;
  Src = 0;
  SourceString = 0;
  Handle = 0;
  v34 = 0;
  v16 = a10;
  if ( a10 )
    *a10 = 0;
  if ( !a2 )
  {
    NormalizedNtPath = -2147024809;
    v38 = -2147024809;
    HIWORD(v39) = 1279;
    goto LABEL_54;
  }
  v38 = 0;
  LOWORD(v39) = 1279;
  if ( a5 )
  {
    NormalizedNtPath = CPathUtilities::GetNormalizedNtPath(a5, &Src);
    v38 = NormalizedNtPath;
    v18 = NormalizedNtPath < 0;
    v19 = 1289;
  }
  else
  {
    NormalizedNtPath = CPathUtilities::GetAbsoluteFileName(this[1], a2, &Src);
    v38 = NormalizedNtPath;
    v18 = NormalizedNtPath < 0;
    v19 = 1295;
  }
  if ( v18 )
    goto LABEL_16;
  LOWORD(v39) = v19;
  if ( a4 )
  {
    NormalizedNtPath = CPathUtilities::GetNormalizedNtPath(a4, (unsigned __int16 **)&SourceString);
    v38 = NormalizedNtPath;
    v20 = NormalizedNtPath < 0;
    v19 = 1304;
  }
  else
  {
    if ( !a3 )
    {
      v21 = Src;
      goto LABEL_25;
    }
    NormalizedNtPath = CPathUtilities::GetAbsoluteFileName(this[1], a3, (unsigned __int16 **)&SourceString);
    v38 = NormalizedNtPath;
    v20 = NormalizedNtPath < 0;
    v19 = 1318;
  }
  if ( v20 )
    goto LABEL_16;
  LOWORD(v39) = v19;
  v21 = SourceString;
LABEL_25:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      26,
      (unsigned int)WPP_bfe3f9d07e6736223889f9787b891edb_Traceguids,
      (_DWORD)v21,
      (__int64)Src);
  }
  v22 = SecurityDescriptor;
  v23 = SecurityDescriptor != 0 ? 1376641 : 1114497;
  a7 = 0;
  NormalizedNtPath = (*(__int64 (__fastcall **)(struct IFspFile *, unsigned int *))(*(_QWORD *)a2 + 40LL))(a2, &a7);
  v38 = NormalizedNtPath;
  v19 = 1370;
  if ( NormalizedNtPath < 0 )
    goto LABEL_16;
  LOWORD(v39) = 1370;
  v25 = a6;
  v26 = v23 | 2;
  if ( (a6 & 0x800) == 0 )
    v26 = v23;
  NormalizedNtPath = CFspFileSystemOperations::CreateFileW(
                       v21,
                       v26,
                       v24,
                       (a7 & 0x10) != 0 ? 3 : 0,
                       0x2Au,
                       v33,
                       8u,
                       &Handle);
  v38 = NormalizedNtPath;
  v19 = 1403;
  if ( NormalizedNtPath < 0 )
    goto LABEL_16;
  LOWORD(v39) = 1403;
  if ( a3 )
  {
    NormalizedNtPath = CNtfsFileSystemApplier::ValidateFileUnchanged(v27, Handle, a3);
    v38 = NormalizedNtPath;
    v19 = 1415;
    if ( NormalizedNtPath < 0 )
      goto LABEL_16;
    LOWORD(v39) = 1415;
  }
  if ( !a6 )
  {
    NormalizedNtPath = CFspFileSystemOperations::GetAttributes(Handle, &v34);
    v38 = NormalizedNtPath;
    v19 = 1429;
    if ( NormalizedNtPath < 0 )
      goto LABEL_16;
    LOWORD(v39) = 1429;
    v25 = v34 & 0x6820;
  }
  if ( v22 )
  {
    v28 = NtSetSecurityObject(Handle, SecurityInformation, v22);
    NormalizedNtPath = HRESULTFromNTSTATUS(v28);
    v38 = NormalizedNtPath;
    v19 = 1443;
    if ( NormalizedNtPath < 0 )
      goto LABEL_16;
    LOWORD(v39) = 1443;
  }
  v29 = (char *)((char *)Src - (char *)v21);
  do
  {
    v30 = *(unsigned __int16 *)&v29[(_QWORD)v21];
    v31 = *v21 - v30;
    if ( v31 )
      break;
    ++v21;
  }
  while ( v30 );
  if ( v31 )
  {
    NormalizedNtPath = CFspFileSystemOperations::Rename(Handle, Src);
    v38 = NormalizedNtPath;
    v19 = 1454;
    if ( NormalizedNtPath < 0 )
      goto LABEL_16;
    LOWORD(v39) = 1454;
  }
  NormalizedNtPath = CFspFileSystemOperations::SetInformation(Handle, a2, v25);
  v38 = NormalizedNtPath;
  v19 = 1464;
  if ( NormalizedNtPath < 0 )
    goto LABEL_16;
  LOWORD(v39) = 1464;
  if ( !v16 )
    goto LABEL_52;
  NormalizedNtPath = CNtfsFileSystemApplier::CloseActionHandleAndGetConcurrencyBlob(
                       (CNtfsFileSystemApplier *)this,
                       &Handle,
                       Src,
                       v16);
  v38 = NormalizedNtPath;
  v19 = 1471;
  if ( NormalizedNtPath < 0 )
  {
LABEL_16:
    HIWORD(v39) = v19;
    goto LABEL_52;
  }
  LOWORD(v39) = 1471;
LABEL_52:
  if ( Handle )
  {
    NtClose(Handle);
    Handle = 0;
    NormalizedNtPath = v38;
  }
LABEL_54:
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&SourceString);
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&Src);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v38);
  return (unsigned int)NormalizedNtPath;
}

```

## disassembly

```asm
0x18011038c  mov     [rsp-38h+arg_10], rbx
0x180110391  mov     [rsp-38h+arg_8], rdx
0x180110396  mov     [rsp-38h+arg_0], rcx
0x18011039b  push    rbp
0x18011039c  push    rsi
0x18011039d  push    rdi
0x18011039e  push    r12
0x1801103a0  push    r13
0x1801103a2  push    r14
0x1801103a4  push    r15
0x1801103a6  mov     rbp, rsp
0x1801103a9  sub     rsp, 80h
0x1801103b0  mov     rdi, r9
0x1801103b3  mov     r15, r8
0x1801103b6  mov     rsi, rdx
0x1801103b9  mov     r14, rcx
0x1801103bc  lea     rcx, WPP_GLOBAL_Control
0x1801103c3  mov     r12d, 100h
0x1801103c9  mov     rax, cs:WPP_GLOBAL_Control
0x1801103d0  cmp     rax, rcx
0x1801103d3  jz      short loc_1801103FD
0x1801103d5  test    [rax+44h], r12d
0x1801103d9  jz      short loc_18011040D
0x1801103db  cmp     byte ptr [rax+41h], 6
0x1801103df  jb      short loc_1801103FD
0x1801103e1  mov     edx, 19h
0x1801103e6  lea     r8, WPP_bfe3f9d07e6736223889f9787b891edb_Traceguids
0x1801103ed  mov     rcx, [rax+38h]
0x1801103f1  call    WPP_SF_
0x1801103f6  mov     rax, cs:WPP_GLOBAL_Control
0x1801103fd  test    [rax+44h], r12d
0x180110401  jz      short loc_18011040D
0x180110403  cmp     byte ptr [rax+41h], 6
0x180110407  jb      short loc_18011040D
0x180110409  mov     cl, 1
0x18011040b  jmp     short loc_18011040F
0x18011040d  xor     cl, cl
0x18011040f  mov     [rbp+var_20], 0
0x180110416  mov     [rbp+var_1C], 4F6h
0x18011041d  mov     [rbp+var_18], cl
0x180110420  lea     rax, aCntfsfilesyste; "CNtfsFileSystemApplier::UpdateInPlace"
0x180110427  mov     [rbp+var_10], rax
0x18011042b  mov     [rbp+var_8], 0
0x180110433  mov     [rbp+Src], 0
0x18011043b  mov     [rbp+SourceString], 0
0x180110443  mov     [rbp+Handle], 0
0x18011044b  mov     [rbp+var_40], 0
0x180110452  mov     r13, [rbp+arg_48]
0x180110459  test    r13, r13
0x18011045c  jz      short loc_180110466
0x18011045e  mov     qword ptr [r13+0], 0
0x180110466  mov     eax, 4FFh
0x18011046b  test    rsi, rsi
0x18011046e  jnz     short loc_180110481
0x180110470  mov     ebx, 80070057h
0x180110475  mov     [rbp+var_20], ebx
0x180110478  mov     word ptr [rbp+var_1C+2], ax
0x18011047c  jmp     loc_180110744
0x180110481  mov     [rbp+var_20], 0
0x180110488  mov     word ptr [rbp+var_1C], ax
0x18011048c  mov     rcx, [rbp+arg_20]; unsigned __int16 *
0x180110490  test    rcx, rcx
0x180110493  jz      short loc_1801104B5
0x180110495  lea     rdx, [rbp+Src]; unsigned __int16 **
0x180110499  call    ?GetNormalizedNtPath@CPathUtilities@@SAJPEBGPEAPEAG@Z; CPathUtilities::GetNormalizedNtPath(ushort const *,ushort * *)
0x18011049e  mov     ebx, eax
0x1801104a0  mov     [rbp+var_20], eax
0x1801104a3  test    eax, eax
0x1801104a5  mov     eax, 509h
0x1801104aa  jns     short loc_1801104D3
0x1801104ac  mov     word ptr [rbp+var_1C+2], ax
0x1801104b0  jmp     loc_18011072A
0x1801104b5  lea     r8, [rbp+Src]; unsigned __int16 **
0x1801104b9  mov     rdx, rsi; struct IFspFile *
0x1801104bc  mov     rcx, [r14+8]; unsigned __int16 *
0x1801104c0  call    ?GetAbsoluteFileName@CPathUtilities@@SAJPEBGPEAUIFspFile@@PEAPEAG@Z; CPathUtilities::GetAbsoluteFileName(ushort const *,IFspFile *,ushort * *)
0x1801104c5  mov     ebx, eax
0x1801104c7  mov     [rbp+var_20], eax
0x1801104ca  test    eax, eax
0x1801104cc  mov     eax, 50Fh
0x1801104d1  jmp     short loc_1801104AA
0x1801104d3  mov     word ptr [rbp+var_1C], ax
0x1801104d7  test    rdi, rdi
0x1801104da  jz      short loc_180110500
0x1801104dc  lea     rdx, [rbp+SourceString]; unsigned __int16 **
0x1801104e0  mov     rcx, rdi; unsigned __int16 *
0x1801104e3  call    ?GetNormalizedNtPath@CPathUtilities@@SAJPEBGPEAPEAG@Z; CPathUtilities::GetNormalizedNtPath(ushort const *,ushort * *)
0x1801104e8  mov     ebx, eax
0x1801104ea  mov     [rbp+var_20], eax
0x1801104ed  test    eax, eax
0x1801104ef  mov     eax, 518h
0x1801104f4  js      short loc_1801104AC
0x1801104f6  mov     word ptr [rbp+var_1C], ax
0x1801104fa  mov     rdi, [rbp+SourceString]
0x1801104fe  jmp     short loc_180110527
0x180110500  test    r15, r15
0x180110503  jz      short loc_180110523
0x180110505  lea     r8, [rbp+SourceString]; unsigned __int16 **
0x180110509  mov     rdx, r15; struct IFspFile *
0x18011050c  mov     rcx, [r14+8]; unsigned __int16 *
0x180110510  call    ?GetAbsoluteFileName@CPathUtilities@@SAJPEBGPEAUIFspFile@@PEAPEAG@Z; CPathUtilities::GetAbsoluteFileName(ushort const *,IFspFile *,ushort * *)
0x180110515  mov     ebx, eax
0x180110517  mov     [rbp+var_20], eax
0x18011051a  test    eax, eax
0x18011051c  mov     eax, 526h
0x180110521  jmp     short loc_1801104F4
0x180110523  mov     rdi, [rbp+Src]
0x180110527  mov     rcx, cs:WPP_GLOBAL_Control
0x18011052e  lea     rax, WPP_GLOBAL_Control
0x180110535  cmp     rcx, rax
0x180110538  jz      short loc_180110567
0x18011053a  test    [rcx+44h], r12d
0x18011053e  jz      short loc_180110567
0x180110540  cmp     byte ptr [rcx+41h], 4
0x180110544  jb      short loc_180110567
0x180110546  mov     edx, 1Ah
0x18011054b  mov     rax, [rbp+Src]
0x18011054f  mov     qword ptr [rsp+80h+var_60], rax
0x180110554  mov     r9, rdi
0x180110557  lea     r8, WPP_bfe3f9d07e6736223889f9787b891edb_Traceguids
0x18011055e  mov     rcx, [rcx+38h]
0x180110562  call    WPP_SF_SS
0x180110567  mov     r12, [rbp+SecurityDescriptor]
0x18011056b  mov     rax, r12
0x18011056e  neg     rax
0x180110571  sbb     r14d, r14d
0x180110574  and     r14d, 40000h
0x18011057b  add     r14d, 110181h
0x180110582  mov     [rbp+arg_30], 0
0x180110589  mov     rax, [rsi]
0x18011058c  lea     rdx, [rbp+arg_30]
0x180110590  mov     rcx, rsi
0x180110593  mov     rax, [rax+28h]
0x180110597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011059c  mov     ebx, eax
0x18011059e  mov     [rbp+var_20], eax
0x1801105a1  test    eax, eax
0x1801105a3  mov     eax, 55Ah
0x1801105a8  js      loc_1801104AC
0x1801105ae  mov     word ptr [rbp+var_1C], ax
0x1801105b2  mov     eax, [rbp+arg_30]
0x1801105b5  and     al, 10h
0x1801105b7  neg     al
0x1801105b9  sbb     r9d, r9d
0x1801105bc  and     r9d, 3; unsigned int
0x1801105c0  mov     esi, [rbp+arg_28]
0x1801105c3  mov     edx, r14d
0x1801105c6  or      edx, 2
0x1801105c9  bt      esi, 0Bh
0x1801105cd  cmovnb  edx, r14d; DesiredAccess
0x1801105d1  lea     rax, [rbp+Handle]
0x1801105d5  mov     [rsp+80h+var_48], rax; void **
0x1801105da  mov     [rsp+80h+var_50], 8; unsigned int
0x1801105e2  mov     [rsp+80h+var_60], 2Ah ; '*'; ULONG
0x1801105ea  mov     rcx, rdi; SourceString
0x1801105ed  call    ?CreateFileW@CFspFileSystemOperations@@SAJPEBGKKKKKKPEAPEAX@Z; CFspFileSystemOperations::CreateFileW(ushort const *,ulong,ulong,ulong,ulong,ulong,ulong,void * *)
0x1801105f2  mov     ebx, eax
0x1801105f4  mov     [rbp+var_20], eax
0x1801105f7  test    eax, eax
0x1801105f9  mov     eax, 57Bh
0x1801105fe  js      loc_1801104AC
0x180110604  mov     word ptr [rbp+var_1C], ax
0x180110608  test    r15, r15
0x18011060b  jz      short loc_18011062F
0x18011060d  mov     r8, r15; struct IFspInPlaceFile *
0x180110610  mov     rdx, [rbp+Handle]; void *
0x180110614  call    ?ValidateFileUnchanged@CNtfsFileSystemApplier@@AEAAJPEAXPEAUIFspInPlaceFile@@@Z; CNtfsFileSystemApplier::ValidateFileUnchanged(void *,IFspInPlaceFile *)
0x180110619  mov     ebx, eax
0x18011061b  mov     [rbp+var_20], eax
0x18011061e  test    eax, eax
0x180110620  mov     eax, 587h
0x180110625  js      loc_1801104AC
0x18011062b  mov     word ptr [rbp+var_1C], ax
0x18011062f  test    esi, esi
0x180110631  jnz     short loc_18011065F
0x180110633  lea     rdx, [rbp+var_40]; unsigned int *
0x180110637  mov     rcx, [rbp+Handle]; FileHandle
0x18011063b  call    ?GetAttributes@CFspFileSystemOperations@@SAJPEAXPEAK@Z; CFspFileSystemOperations::GetAttributes(void *,ulong *)
0x180110640  mov     ebx, eax
0x180110642  mov     [rbp+var_20], eax
0x180110645  test    eax, eax
0x180110647  mov     eax, 595h
0x18011064c  js      loc_1801104AC
0x180110652  mov     word ptr [rbp+var_1C], ax
0x180110656  mov     esi, [rbp+var_40]
0x180110659  and     esi, 6820h
0x18011065f  test    r12, r12
0x180110662  jz      short loc_180110694
0x180110664  mov     r8, r12; SecurityDescriptor
0x180110667  mov     edx, [rbp+SecurityInformation]; SecurityInformation
0x18011066d  mov     rcx, [rbp+Handle]; Handle
0x180110671  call    cs:__imp_NtSetSecurityObject
0x180110677  mov     ecx, eax
0x180110679  call    HRESULTFromNTSTATUS
0x18011067e  mov     ebx, eax
0x180110680  mov     [rbp+var_20], eax
0x180110683  test    eax, eax
0x180110685  mov     eax, 5A3h
0x18011068a  js      loc_1801104AC
0x180110690  mov     word ptr [rbp+var_1C], ax
0x180110694  mov     rdx, [rbp+Src]; Src
0x180110698  mov     r8, rdx
0x18011069b  sub     r8, rdi
0x18011069e  movzx   eax, word ptr [rdi]
0x1801106a1  movzx   ecx, word ptr [rdi+r8]
0x1801106a6  sub     eax, ecx
0x1801106a8  jnz     short loc_1801106B2
0x1801106aa  add     rdi, 2
0x1801106ae  test    ecx, ecx
0x1801106b0  jnz     short loc_18011069E
0x1801106b2  test    eax, eax
0x1801106b4  jz      short loc_1801106D5
0x1801106b6  mov     rcx, [rbp+Handle]; FileHandle
0x1801106ba  call    ?Rename@CFspFileSystemOperations@@SAJPEAXPEBG@Z; CFspFileSystemOperations::Rename(void *,ushort const *)
0x1801106bf  mov     ebx, eax
0x1801106c1  mov     [rbp+var_20], eax
0x1801106c4  test    eax, eax
0x1801106c6  mov     eax, 5AEh
0x1801106cb  js      loc_1801104AC
0x1801106d1  mov     word ptr [rbp+var_1C], ax
0x1801106d5  mov     r8d, esi; unsigned int
0x1801106d8  mov     rdx, [rbp+arg_8]; struct IFspFile *
0x1801106dc  mov     rcx, [rbp+Handle]; FileHandle
0x1801106e0  call    ?SetInformation@CFspFileSystemOperations@@SAJPEAXPEAUIFspFile@@K@Z; CFspFileSystemOperations::SetInformation(void *,IFspFile *,ulong)
0x1801106e5  mov     ebx, eax
0x1801106e7  mov     [rbp+var_20], eax
0x1801106ea  test    eax, eax
0x1801106ec  mov     eax, 5B8h
0x1801106f1  js      loc_1801104AC
0x1801106f7  mov     word ptr [rbp+var_1C], ax
0x1801106fb  test    r13, r13
0x1801106fe  jz      short loc_18011072A
0x180110700  mov     r9, r13; struct IFileConcurrencyBlob **
0x180110703  mov     r8, [rbp+Src]; unsigned __int16 *
0x180110707  lea     rdx, [rbp+Handle]; void **
0x18011070b  mov     rcx, [rbp+arg_0]; this
0x18011070f  call    ?CloseActionHandleAndGetConcurrencyBlob@CNtfsFileSystemApplier@@AEAAJPEAPEAXPEBGPEAPEAUIFileConcurrencyBlob@@@Z; CNtfsFileSystemApplier::CloseActionHandleAndGetConcurrencyBlob(void * *,ushort const *,IFileConcurrencyBlob * *)
0x180110714  mov     ebx, eax
0x180110716  mov     [rbp+var_20], eax
0x180110719  test    eax, eax
0x18011071b  mov     eax, 5BFh
0x180110720  js      loc_1801104AC
0x180110726  mov     word ptr [rbp+var_1C], ax
0x18011072a  mov     rcx, [rbp+Handle]; Handle
0x18011072e  test    rcx, rcx
0x180110731  jz      short loc_180110744
0x180110733  call    cs:__imp_NtClose
0x180110739  mov     [rbp+Handle], 0
0x180110741  mov     ebx, [rbp+var_20]
0x180110744  lea     rcx, [rbp+SourceString]
0x180110748  call    ??1?$CEcsMemPtr@G$0A@@@QEAA@XZ; CEcsMemPtr<ushort,0>::~CEcsMemPtr<ushort,0>(void)
0x18011074d  lea     rcx, [rbp+Src]
0x180110751  call    ??1?$CEcsMemPtr@G$0A@@@QEAA@XZ; CEcsMemPtr<ushort,0>::~CEcsMemPtr<ushort,0>(void)
0x180110756  lea     rcx, [rbp+var_20]; this
0x18011075a  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18011075f  mov     eax, ebx
0x180110761  mov     rbx, [rsp+80h+arg_10]
0x180110769  add     rsp, 80h
0x180110770  pop     r15
0x180110772  pop     r14
0x180110774  pop     r13
0x180110776  pop     r12
0x180110778  pop     rdi
0x180110779  pop     rsi
0x18011077a  pop     rbp
0x18011077b  retn
```
