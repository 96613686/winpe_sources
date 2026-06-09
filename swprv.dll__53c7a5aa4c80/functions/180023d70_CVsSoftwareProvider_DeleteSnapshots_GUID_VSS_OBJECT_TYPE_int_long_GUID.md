# CVsSoftwareProvider::DeleteSnapshots(_GUID,_VSS_OBJECT_TYPE,int,long *,_GUID *)

- ea: `0x180023d70`
- end: `0x180024323`
- name: `?DeleteSnapshots@CVsSoftwareProvider@@UEAAJU_GUID@@W4_VSS_OBJECT_TYPE@@HPEAJPEAU2@@Z`
- size: `1459`
- prototype: `__int64 __fastcall(CVsSoftwareProvider *__hidden this, struct _GUID *, enum _VSS_OBJECT_TYPE, int, int *, struct _GUID *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000212c`
- `0x1800034cc`
- `0x180003888`
- `0x1800108d4`
- `0x180010974`
- `0x180023d70`
- `0x180024a6c`
- `0x180033a8c`
- `0x180033c78`
- `0x180034a4c`
- `0x18003649c`
- `0x1800367b8`
- `0x18003d78c`

## string_xrefs

- `0x180023daa`: `CVsSoftwareProvider::DeleteSnapshots`
- `0x180023e8d`: `CVsSoftwareProvider::DeleteSnapshots`
- `0x180023fb4`: `CVsSoftwareProvider::DeleteSnapshots`
- `0x18002404c`: `CVsSoftwareProvider::DeleteSnapshots`
- `0x1800240f0`: `CVsSoftwareProvider::DeleteSnapshots`
- `0x180024173`: `CVsSoftwareProvider::DeleteSnapshots`
- `0x180024223`: `CVsSoftwareProvider::DeleteSnapshots`
- `0x180023d9c`: `base\stor\vss\modules\softprv\src\delete.cxx`
- `0x180023e7e`: `base\stor\vss\modules\softprv\src\delete.cxx`
- `0x180023fa5`: `base\stor\vss\modules\softprv\src\delete.cxx`
- `0x18002403d`: `base\stor\vss\modules\softprv\src\delete.cxx`
- `0x1800240e1`: `base\stor\vss\modules\softprv\src\delete.cxx`
- `0x180024214`: `base\stor\vss\modules\softprv\src\delete.cxx`
- `0x180023f80`: `Parameters:   SourceObjectId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}  eSourceObjectType = %d  bForceDelete = %s  plDeletedSnapshots = %p  pNondeletedSnapshotID = %p`
- `0x180024012`: `plDeletedSnapshots == NULL`
- `0x1800240aa`: `pNondeletedSnapshotID == NULL`
- `0x180024282`: `Incompatible type %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVsSoftwareProvider::DeleteSnapshots(
        CVsSoftwareProvider *this,
        struct _GUID *a2,
        enum _VSS_OBJECT_TYPE a3,
        int a4,
        int *a5,
        struct _GUID *a6)
{
  bool v9; // dl
  unsigned int v10; // ecx
  bool v11; // al
  const wchar_t *v12; // r14
  int ContextInternal; // eax
  unsigned int v14; // ebx
  struct _GUID *v16; // [rsp+20h] [rbp-1E8h]
  const unsigned __int16 *v17; // [rsp+90h] [rbp-178h] BYREF
  const unsigned __int16 *v18; // [rsp+98h] [rbp-170h]
  const unsigned __int16 *v19; // [rsp+A0h] [rbp-168h]
  int v20; // [rsp+A8h] [rbp-160h]
  int v21; // [rsp+ACh] [rbp-15Ch]
  int v22; // [rsp+B0h] [rbp-158h]
  _BYTE v23[120]; // [rsp+B8h] [rbp-150h] BYREF
  int v24; // [rsp+130h] [rbp-D8h]
  int v25; // [rsp+138h] [rbp-D0h] BYREF
  struct _GUID Buf2; // [rsp+140h] [rbp-C8h] BYREF
  LPVOID v27; // [rsp+150h] [rbp-B8h] BYREF
  unsigned int v28; // [rsp+158h] [rbp-B0h]
  unsigned int v29; // [rsp+174h] [rbp-94h]
  _com_error *v30; // [rsp+1C0h] [rbp-48h] BYREF
  const std::exception *v31; // [rsp+1C8h] [rbp-40h] BYREF
  LPCRITICAL_SECTION v32[2]; // [rsp+1D0h] [rbp-38h] BYREF

  v17 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
  v18 = L"CVsSoftwareProvider::DeleteSnapshots";
  v19 = L"SPRDELEC";
  v20 = 93;
  v21 = 2;
  v22 = 255;
  v24 = 0x1000000;
  memset_0(v23, 0, sizeof(v23));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v27, (__int64)&v17, 0);
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = GUID_NULL;
  try
  {
    v11 = IsInGroup(v10, v9);
    v21 = 2;
    v22 = 255;
    v24 = 0x1000000;
    v17 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
    v18 = L"CVsSoftwareProvider::DeleteSnapshots";
    v19 = L"SPRDELEC";
    if ( !v11 )
    {
      v20 = 103;
      memset_0(v23, 0, sizeof(v23));
      CVssFunctionTracer::Throw(
        &v27,
        &v17,
        2147942405LL,
        L"The client process is not running under an administrator account");
    }
    v20 = 107;
    memset_0(v23, 0, sizeof(v23));
    v12 = L"TRUE";
    if ( !a4 )
      v12 = L"FALSE";
    CVssFunctionTracer::Trace(
      &v27,
      &v17,
      L"Parameters:   SourceObjectId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}  eSourceObjectType = %d  bForceD"
       "elete = %s  plDeletedSnapshots = %p  pNondeletedSnapshotID = %p",
      a2->Data1,
      a2->Data2,
      a2->Data3,
      a2->Data4[0],
      a2->Data4[1],
      a2->Data4[2],
      a2->Data4[3],
      a2->Data4[4],
      a2->Data4[5],
      a2->Data4[6],
      a2->Data4[7],
      a3,
      v12,
      a5,
      a6);
    if ( !a5 )
    {
      v17 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
      v18 = L"CVsSoftwareProvider::DeleteSnapshots";
      v19 = L"SPRDELEC";
      v20 = 123;
      v21 = 2;
      v22 = 255;
      v24 = 0x1000000;
      memset_0(v23, 0, sizeof(v23));
      CVssFunctionTracer::Throw(&v27, &v17, 2147942487LL, L"plDeletedSnapshots == NULL");
    }
    if ( !a6 )
    {
      v17 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
      v18 = L"CVsSoftwareProvider::DeleteSnapshots";
      v19 = L"SPRDELEC";
      v20 = 126;
      v21 = 2;
      v22 = 255;
      v24 = 0x1000000;
      memset_0(v23, 0, sizeof(v23));
      CVssFunctionTracer::Throw(&v27, &v17, 2147942487LL, L"pNondeletedSnapshotID == NULL");
    }
    CVssAutomaticLock2::CVssAutomaticLock2(
      (CVssAutomaticLock2 *)v32,
      (struct CVssCriticalSection *)CVsSoftwareProvider::m_cs);
    v17 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
    v18 = L"CVsSoftwareProvider::DeleteSnapshots";
    v19 = L"SPRDELEC";
    v20 = 130;
    v21 = 2;
    v22 = 255;
    v24 = 0x1000000;
    memset_0(v23, 0, sizeof(v23));
    CVssFunctionTracer::AddOperation((struct CVssFunctionTracer *)&v27, (const struct CVssDebugInfo *)&v17, 305);
    v17 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
    v18 = L"CVsSoftwareProvider::DeleteSnapshots";
    v19 = L"SPRDELEC";
    v20 = 131;
    v21 = 2;
    v22 = 255;
    v24 = 0x1000000;
    memset_0(v23, 0, sizeof(v23));
    CVssFunctionTracer::AddOperation(
      (struct CVssFunctionTracer *)&v27,
      (const struct CVssDebugInfo *)&v17,
      5012,
      L"System Provider");
    CVsSoftwareProvider::FreezeContext(this);
    if ( a3 != VSS_OBJECT_SNAPSHOT_SET && a3 != VSS_OBJECT_SNAPSHOT )
    {
      v17 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
      v18 = L"CVsSoftwareProvider::DeleteSnapshots";
      v19 = L"SPRDELEC";
      v20 = 150;
      v21 = 2;
      v22 = 255;
      v24 = 0x1000000;
      memset_0(v23, 0, sizeof(v23));
      LODWORD(v16) = a3;
      CVssFunctionTracer::Throw(&v27, &v17, 2147942487LL, L"Incompatible type %d", v16);
    }
    ContextInternal = CVsSoftwareProvider::GetContextInternal(this);
    Buf2 = *a2;
    v28 = CVsSoftwareProvider::InternalDeleteSnapshots(&Buf2, a3, ContextInternal, a5, a6);
    CVssAutomaticLock2::~CVssAutomaticLock2(v32);
  }
  catch ( long v25 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v27,
      v25,
      L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx",
      L"SPRDELEC",
      L"CVsSoftwareProvider::DeleteSnapshots",
      0x9Au,
      v29);
  }
  catch ( _com_error *v30 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v27,
      v30,
      L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx",
      L"SPRDELEC",
      L"CVsSoftwareProvider::DeleteSnapshots",
      0x9Au,
      v29);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v27,
      L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx",
      L"SPRDELEC",
      L"CVsSoftwareProvider::DeleteSnapshots",
      0x9Au,
      v29);
  }
  catch ( const std::exception *v31 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v27,
      v31,
      L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx",
      L"SPRDELEC",
      L"CVsSoftwareProvider::DeleteSnapshots",
      0x9Au,
      v29);
  }
  v11 = IsInGroup(v10, v9);
  v21 = 2;
  v22 = 255;
}

```

## disassembly

```asm
0x180023d70  mov     r11, rsp
0x180023d73  mov     [r11+18h], rbx
0x180023d77  mov     [r11+20h], rsi
0x180023d7b  mov     [r11+10h], rdx
0x180023d7f  mov     [r11+8], rcx
0x180023d83  push    rdi
0x180023d84  push    r12
0x180023d86  push    r13
0x180023d88  push    r14
0x180023d8a  push    r15
0x180023d8c  sub     rsp, 1E0h
0x180023d93  mov     ebx, r9d
0x180023d96  mov     r12d, r8d
0x180023d99  mov     rsi, rdx
0x180023d9c  lea     rax, aBaseStorVssMod_5; "base\\stor\\vss\\modules\\softprv\\src"...
0x180023da3  mov     [r11-178h], rax
0x180023daa  lea     rax, aCvssoftwarepro_19; "CVsSoftwareProvider::DeleteSnapshots"
0x180023db1  mov     [r11-170h], rax
0x180023db8  lea     rax, aSprdelec; "SPRDELEC"
0x180023dbf  mov     [r11-168h], rax
0x180023dc6  mov     [rsp+208h+var_160], 5Dh ; ']'
0x180023dd1  mov     r14d, 2
0x180023dd7  mov     [r11-15Ch], r14d
0x180023dde  mov     [rsp+208h+var_158], 0FFh
0x180023de9  mov     [rsp+208h+var_D8], 1000000h
0x180023df4  xor     edx, edx; Val
0x180023df6  lea     r8d, [r14+76h]; Size
0x180023dfa  lea     rcx, [r11-150h]; void *
0x180023e01  call    memset_0
0x180023e06  xor     r8d, r8d
0x180023e09  lea     rdx, [rsp+208h+var_178]
0x180023e11  lea     rcx, [rsp+208h+var_B8]
0x180023e19  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180023e1e  nop
0x180023e1f  mov     r13, [rsp+208h+arg_20]
0x180023e27  test    r13, r13
0x180023e2a  jz      short loc_180023E32
0x180023e2c  xor     eax, eax
0x180023e2e  mov     [r13+0], eax
0x180023e32  mov     r15, [rsp+208h+arg_28]
0x180023e3a  test    r15, r15
0x180023e3d  jz      short loc_180023E4B
0x180023e3f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180023e46  movdqu  xmmword ptr [r15], xmm0
0x180023e4b  call    ?IsInGroup@@YA_NK_N@Z; IsInGroup(ulong,bool)
0x180023e50  mov     [rsp+208h+var_15C], r14d
0x180023e58  mov     [rsp+208h+var_158], 0FFh
0x180023e63  mov     [rsp+208h+var_D8], 1000000h
0x180023e6e  xor     edx, edx; Val
0x180023e70  lea     r8d, [rdx+78h]; Size
0x180023e74  lea     rcx, [rsp+208h+var_150]; void *
0x180023e7c  test    al, al
0x180023e7e  lea     rax, aBaseStorVssMod_5; "base\\stor\\vss\\modules\\softprv\\src"...
0x180023e85  mov     [rsp+208h+var_178], rax
0x180023e8d  lea     rax, aCvssoftwarepro_19; "CVsSoftwareProvider::DeleteSnapshots"
0x180023e94  mov     [rsp+208h+var_170], rax
0x180023e9c  lea     rax, aSprdelec; "SPRDELEC"
0x180023ea3  mov     [rsp+208h+var_168], rax
0x180023eab  jnz     short loc_180023EDF
0x180023ead  mov     [rsp+208h+var_160], 67h ; 'g'
0x180023eb8  call    memset_0
0x180023ebd  lea     r9, aTheClientProce_0; "The client process is not running under"...
0x180023ec4  mov     r8d, 80070005h
0x180023eca  lea     rdx, [rsp+208h+var_178]
0x180023ed2  lea     rcx, [rsp+208h+var_B8]
0x180023eda  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180023edf  mov     [rsp+208h+var_160], 6Bh ; 'k'
0x180023eea  call    memset_0
0x180023eef  lea     rax, aFalse; "FALSE"
0x180023ef6  lea     r14, aTrue; "TRUE"
0x180023efd  test    ebx, ebx
0x180023eff  cmovz   r14, rax
0x180023f03  movzx   eax, byte ptr [rsi+0Fh]
0x180023f07  movzx   ecx, byte ptr [rsi+0Eh]
0x180023f0b  movzx   edx, byte ptr [rsi+0Dh]
0x180023f0f  movzx   r8d, byte ptr [rsi+0Ch]
0x180023f14  movzx   r9d, byte ptr [rsi+0Bh]
0x180023f19  movzx   r10d, byte ptr [rsi+0Ah]
0x180023f1e  movzx   r11d, byte ptr [rsi+9]
0x180023f23  movzx   ebx, byte ptr [rsi+8]
0x180023f27  movzx   edi, word ptr [rsi+6]
0x180023f2b  movzx   esi, word ptr [rsi+4]
0x180023f2f  mov     [rsp+208h+var_180], r15
0x180023f37  mov     [rsp+208h+var_188], r13
0x180023f3f  mov     [rsp+208h+var_190], r14
0x180023f44  mov     [rsp+208h+var_198], r12d
0x180023f49  mov     [rsp+208h+var_1A0], eax
0x180023f4d  mov     [rsp+208h+var_1A8], ecx
0x180023f51  mov     [rsp+208h+var_1B0], edx
0x180023f55  mov     [rsp+208h+var_1B8], r8d
0x180023f5a  mov     [rsp+208h+var_1C0], r9d
0x180023f5f  mov     [rsp+208h+var_1C8], r10d
0x180023f64  mov     [rsp+208h+var_1D0], r11d
0x180023f69  mov     [rsp+208h+var_1D8], ebx
0x180023f6d  mov     [rsp+208h+var_1E0], edi
0x180023f71  mov     dword ptr [rsp+208h+var_1E8], esi
0x180023f75  mov     rbx, [rsp+208h+arg_8]
0x180023f7d  mov     r9d, [rbx]
0x180023f80  lea     r8, aParametersSour; "Parameters:   SourceObjectId = {%.8x-%."...
0x180023f87  lea     rdx, [rsp+208h+var_178]
0x180023f8f  lea     rcx, [rsp+208h+var_B8]
0x180023f97  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180023f9c  test    r13, r13
0x180023f9f  jnz     loc_180024034
0x180023fa5  lea     rax, aBaseStorVssMod_5; "base\\stor\\vss\\modules\\softprv\\src"...
0x180023fac  mov     [rsp+208h+var_178], rax
0x180023fb4  lea     rax, aCvssoftwarepro_19; "CVsSoftwareProvider::DeleteSnapshots"
0x180023fbb  mov     [rsp+208h+var_170], rax
0x180023fc3  lea     rax, aSprdelec; "SPRDELEC"
0x180023fca  mov     [rsp+208h+var_168], rax
0x180023fd2  mov     [rsp+208h+var_160], 7Bh ; '{'
0x180023fdd  lea     r14d, [r13+2]
0x180023fe1  mov     [rsp+208h+var_15C], r14d
0x180023fe9  mov     [rsp+208h+var_158], 0FFh
0x180023ff4  mov     [rsp+208h+var_D8], 1000000h
0x180023fff  xor     edx, edx; Val
0x180024001  lea     r8d, [r13+78h]; Size
0x180024005  lea     rcx, [rsp+208h+var_150]; void *
0x18002400d  call    memset_0
0x180024012  lea     r9, aPldeletedsnaps; "plDeletedSnapshots == NULL"
0x180024019  mov     r8d, 80070057h
0x18002401f  lea     rdx, [rsp+208h+var_178]
0x180024027  lea     rcx, [rsp+208h+var_B8]
0x18002402f  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180024034  test    r15, r15
0x180024037  jnz     loc_1800240CC
0x18002403d  lea     rax, aBaseStorVssMod_5; "base\\stor\\vss\\modules\\softprv\\src"...
0x180024044  mov     [rsp+208h+var_178], rax
0x18002404c  lea     rax, aCvssoftwarepro_19; "CVsSoftwareProvider::DeleteSnapshots"
0x180024053  mov     [rsp+208h+var_170], rax
0x18002405b  lea     rax, aSprdelec; "SPRDELEC"
0x180024062  mov     [rsp+208h+var_168], rax
0x18002406a  mov     [rsp+208h+var_160], 7Eh ; '~'
0x180024075  lea     r14d, [r15+2]
0x180024079  mov     [rsp+208h+var_15C], r14d
0x180024081  mov     [rsp+208h+var_158], 0FFh
0x18002408c  mov     [rsp+208h+var_D8], 1000000h
0x180024097  xor     edx, edx; Val
0x180024099  lea     r8d, [r15+78h]; Size
0x18002409d  lea     rcx, [rsp+208h+var_150]; void *
0x1800240a5  call    memset_0
0x1800240aa  lea     r9, aPnondeletedsna; "pNondeletedSnapshotID == NULL"
0x1800240b1  mov     r8d, 80070057h
0x1800240b7  lea     rdx, [rsp+208h+var_178]
0x1800240bf  lea     rcx, [rsp+208h+var_B8]
0x1800240c7  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x1800240cc  lea     rdx, ?m_cs@CVsSoftwareProvider@@0VCVssCriticalSection@@A; struct CVssCriticalSection *
0x1800240d3  lea     rcx, [rsp+208h+var_38]; this
0x1800240db  call    ??0CVssAutomaticLock2@@QEAA@AEAVCVssCriticalSection@@@Z; CVssAutomaticLock2::CVssAutomaticLock2(CVssCriticalSection &)
0x1800240e0  nop
0x1800240e1  lea     rdi, aBaseStorVssMod_5; "base\\stor\\vss\\modules\\softprv\\src"...
0x1800240e8  mov     [rsp+208h+var_178], rdi
0x1800240f0  lea     rax, aCvssoftwarepro_19; "CVsSoftwareProvider::DeleteSnapshots"
0x1800240f7  mov     [rsp+208h+var_170], rax
0x1800240ff  lea     rax, aSprdelec; "SPRDELEC"
0x180024106  mov     [rsp+208h+var_168], rax
0x18002410e  mov     [rsp+208h+var_160], 82h
0x180024119  mov     r14d, 2
0x18002411f  mov     [rsp+208h+var_15C], r14d
0x180024127  mov     [rsp+208h+var_158], 0FFh
0x180024132  mov     [rsp+208h+var_D8], 1000000h
0x18002413d  xor     edx, edx; Val
0x18002413f  lea     r8d, [r14+76h]; Size
0x180024143  lea     rcx, [rsp+208h+var_150]; void *
0x18002414b  call    memset_0
0x180024150  mov     r8d, 131h
0x180024156  lea     rdx, [rsp+208h+var_178]
0x18002415e  lea     rcx, [rsp+208h+var_B8]
0x180024166  call    ?AddOperation@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IZZ; CVssFunctionTracer::AddOperation(CVssDebugInfo,uint,...)
0x18002416b  mov     [rsp+208h+var_178], rdi
0x180024173  lea     rax, aCvssoftwarepro_19; "CVsSoftwareProvider::DeleteSnapshots"
0x18002417a  mov     [rsp+208h+var_170], rax
0x180024182  lea     rax, aSprdelec; "SPRDELEC"
0x180024189  mov     [rsp+208h+var_168], rax
0x180024191  mov     [rsp+208h+var_160], 83h
0x18002419c  mov     [rsp+208h+var_15C], r14d
0x1800241a4  mov     [rsp+208h+var_158], 0FFh
0x1800241af  mov     [rsp+208h+var_D8], 1000000h
0x1800241ba  xor     edx, edx; Val
0x1800241bc  lea     r8d, [r14+76h]; Size
0x1800241c0  lea     rcx, [rsp+208h+var_150]; void *
0x1800241c8  call    memset_0
0x1800241cd  lea     r9, aSystemProvider; "System Provider"
0x1800241d4  mov     r8d, 1394h
0x1800241da  lea     rdx, [rsp+208h+var_178]
0x1800241e2  lea     rcx, [rsp+208h+var_B8]
0x1800241ea  call    ?AddOperation@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IZZ; CVssFunctionTracer::AddOperation(CVssDebugInfo,uint,...)
0x1800241ef  mov     rdi, [rsp+208h+arg_0]
0x1800241f7  mov     rcx, rdi; this
0x1800241fa  call    ?FreezeContext@CVsSoftwareProvider@@AEAAXXZ; CVsSoftwareProvider::FreezeContext(void)
0x1800241ff  mov     ecx, r12d
0x180024202  sub     ecx, r14d
0x180024205  jz      loc_1800242A4
0x18002420b  cmp     ecx, 1
0x18002420e  jz      loc_1800242A4
0x180024214  lea     rax, aBaseStorVssMod_5; "base\\stor\\vss\\modules\\softprv\\src"...
0x18002421b  mov     [rsp+208h+var_178], rax
0x180024223  lea     rax, aCvssoftwarepro_19; "CVsSoftwareProvider::DeleteSnapshots"
0x18002422a  mov     [rsp+208h+var_170], rax
0x180024232  lea     rax, aSprdelec; "SPRDELEC"
0x180024239  mov     [rsp+208h+var_168], rax
0x180024241  mov     [rsp+208h+var_160], 96h
0x18002424c  mov     [rsp+208h+var_15C], r14d
0x180024254  mov     [rsp+208h+var_158], 0FFh
0x18002425f  mov     [rsp+208h+var_D8], 1000000h
0x18002426a  xor     edx, edx; Val
0x18002426c  lea     r8d, [r14+76h]; Size
0x180024270  lea     rcx, [rsp+208h+var_150]; void *
0x180024278  call    memset_0
0x18002427d  mov     dword ptr [rsp+208h+var_1E8], r12d
0x180024282  lea     r9, aIncompatibleTy; "Incompatible type %d"
0x180024289  mov     r8d, 80070057h
0x18002428f  lea     rdx, [rsp+208h+var_178]
0x180024297  lea     rcx, [rsp+208h+var_B8]
0x18002429f  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x1800242a4  mov     rcx, rdi; this
0x1800242a7  call    ?GetContextInternal@CVsSoftwareProvider@@AEBAJXZ; CVsSoftwareProvider::GetContextInternal(void)
0x1800242ac  movups  xmm0, xmmword ptr [rbx]
0x1800242af  movdqu  xmmword ptr [rsp+208h+Buf2.Data1], xmm0
0x1800242b8  mov     [rsp+208h+var_1E8], r15; struct _GUID *
0x1800242bd  mov     r9, r13; int *
0x1800242c0  mov     r8d, eax; int
0x1800242c3  mov     edx, r12d; enum _VSS_OBJECT_TYPE
0x1800242c6  lea     rcx, [rsp+208h+Buf2]; Buf2
0x1800242ce  call    ?InternalDeleteSnapshots@CVsSoftwareProvider@@SAJU_GUID@@W4_VSS_OBJECT_TYPE@@JPEAJPEAU2@@Z; CVsSoftwareProvider::InternalDeleteSnapshots(_GUID,_VSS_OBJECT_TYPE,long,long *,_GUID *)
0x1800242d3  mov     [rsp+208h+var_B0], eax
0x1800242da  lea     rcx, [rsp+208h+var_38]; this
0x1800242e2  call    ??1CVssAutomaticLock2@@QEAA@XZ; CVssAutomaticLock2::~CVssAutomaticLock2(void)
0x1800242e7  nop
0x1800242e8  jmp     short loc_1800242F0
0x1800242ea  jmp     short loc_1800242F0
0x1800242ec  jmp     short loc_1800242F0
0x1800242ee  jmp     short $+2
0x1800242f0  mov     ebx, [rsp+208h+var_B0]
0x1800242f7  lea     rcx, [rsp+208h+var_B8]; this
0x1800242ff  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x180024304  mov     eax, ebx
0x180024306  lea     r11, [rsp+208h+var_28]
0x18002430e  mov     rbx, [r11+40h]
0x180024312  mov     rsi, [r11+48h]
0x180024316  mov     rsp, r11
0x180024319  pop     r15
0x18002431b  pop     r14
0x18002431d  pop     r13
0x18002431f  pop     r12
0x180024321  pop     rdi
0x180024322  retn
```
