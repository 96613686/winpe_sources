# DynVolume::Initialize(void *,_GUID *,_GUID *,ushort *)

- ea: `0x1400d4088`
- end: `0x1400d4670`
- name: `?Initialize@DynVolume@@QEAAHPEAXPEAU_GUID@@1PEAG@Z`
- size: `1512`
- prototype: `int(DynVolume *__hidden this, void *, struct _GUID *, struct _GUID *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1400d365c`

## callees

- `0x1400212d4`
- `0x140021ca0`
- `0x1400235a8`
- `0x14003b0c0`
- `0x140091560`
- `0x1400919a0`
- `0x1400919c4`
- `0x1400921dc`
- `0x1400d2554`
- `0x1400d257c`
- `0x1400d3354`
- `0x1400d4044`
- `0x1400d4088`
- `0x1400d4678`
- `0x1400d54d0`
- `0x1400d7a34`
- `0x1400d7aac`
- `0x1400d969c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d4346`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d4648`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d4346`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d4648`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d413c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d4165`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d41fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d4215`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d43fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d4420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d413c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d4165`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d41fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d4215`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d43fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d4420`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d461e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d4627`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d461e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d4627`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DynVolume::Initialize(
        DynVolume *this,
        void *a2,
        struct _GUID *a3,
        struct _GUID *a4,
        unsigned __int16 *a5)
{
  unsigned __int16 *v7; // rdi
  char *v8; // r14
  DynPlex *v9; // r15
  unsigned __int16 *v10; // r13
  unsigned int v11; // esi
  DWORD LastError; // edi
  DWORD v13; // eax
  DWORD v14; // eax
  const unsigned __int16 *v15; // rsi
  int v16; // r8d
  __int64 v17; // rax
  DWORD v18; // ecx
  unsigned __int64 v19; // rdi
  __int64 v20; // rax
  bool v21; // cf
  unsigned __int64 v22; // rax
  unsigned __int16 *v23; // rax
  struct _VM_PLEX_LAYOUT *v24; // rdi
  unsigned int i; // r12d
  DWORD v26; // eax
  DynVolume *v27; // rcx
  struct _DRIVE_LAYOUT_INFORMATION_EX *v28; // rcx
  int v29; // edx
  const char *v30; // rax
  int v31; // r9d
  unsigned int v32; // edx
  void *v34; // [rsp+30h] [rbp-A1h] BYREF
  unsigned __int16 *v35; // [rsp+38h] [rbp-99h] BYREF
  HANDLE hDevice; // [rsp+40h] [rbp-91h]
  struct _GUID *v37; // [rsp+48h] [rbp-89h]
  DynVolume *v38; // [rsp+50h] [rbp-81h]
  struct _GUID *v39; // [rsp+58h] [rbp-79h]
  struct _GUID InBuffer; // [rsp+60h] [rbp-71h] BYREF
  struct _GUID v41; // [rsp+70h] [rbp-61h]
  unsigned __int16 v42; // [rsp+80h] [rbp-51h] BYREF
  _BYTE v43[78]; // [rsp+82h] [rbp-4Fh] BYREF

  v39 = a4;
  v37 = a3;
  hDevice = a2;
  v38 = this;
  v7 = a5;
  TraceFunctionEnter(L"DynVolume::Initialize");
  InBuffer = 0;
  v41 = 0;
  v8 = 0;
  v34 = 0;
  v9 = 0;
  v10 = 0;
  v35 = 0;
  v42 = 0;
  memset_0(v43, 0, 0x48u);
  if ( !a3 )
  {
    v11 = 0;
    v31 = 87;
    LastError = 87;
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_64;
    }
    v29 = 53;
    v30 = "pPackId";
LABEL_63:
    WPP_SF_Ds(
      *(_QWORD *)v28->Gpt.DiskId.Data4,
      v29,
      (unsigned int)WPP_b771bf60a8233494a340a3d0d6c7ca4f_Traceguids,
      v31,
      v30);
    goto LABEL_64;
  }
  if ( !a4 )
  {
    v11 = 0;
    v31 = 87;
    LastError = 87;
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_64;
    }
    v29 = 54;
    v30 = "pVolId";
    goto LABEL_63;
  }
  if ( !a5 )
  {
    v11 = 0;
    v31 = 87;
    LastError = 87;
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_64;
    }
    v29 = 55;
    v30 = "pmwszCriticalVolumes";
    goto LABEL_63;
  }
  if ( !SafeStrConvertGuidString(a4, &v42, 0x25u) )
  {
    v11 = 0;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v13 = GetLastError();
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        56,
        (unsigned int)WPP_b771bf60a8233494a340a3d0d6c7ca4f_Traceguids,
        v13,
        "SafeStrConvertGuidString(pVolId, ARRAY_COUNT_PARAM(wszGuidString))");
    }
    goto LABEL_64;
  }
  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x200000000LL) != 0 )
  {
    WPP_SF_S(*(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4, 57, WPP_b771bf60a8233494a340a3d0d6c7ca4f_Traceguids, &v42);
  }
  InBuffer = *a3;
  v41 = *a4;
  if ( !(unsigned int)DoIoctlCall(hDevice, 0x764338u, &InBuffer, 0x20u, &v34) )
  {
    v11 = 0;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v14 = GetLastError();
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        58,
        (unsigned int)WPP_b771bf60a8233494a340a3d0d6c7ca4f_Traceguids,
        v14,
        "GetLastError()");
    }
    v8 = (char *)v34;
    goto LABEL_64;
  }
  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x200000000LL) != 0 )
  {
    WPP_SF_(*(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4, 59, WPP_b771bf60a8233494a340a3d0d6c7ca4f_Traceguids);
  }
  v8 = (char *)v34;
  TraceQueryVolumeInfoBuffer(v34, a4);
  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x200000000LL) != 0 )
  {
    WPP_SF_(*(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4, 60, WPP_b771bf60a8233494a340a3d0d6c7ca4f_Traceguids);
  }
  v15 = (const unsigned __int16 *)&v8[*((unsigned int *)v8 + 3)];
  if ( !(unsigned int)MtMgrGetSymbolicNames(v15, &v35)
    && WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x200000000LL) != 0 )
  {
    WPP_SF_S(*(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4, 61, WPP_b771bf60a8233494a340a3d0d6c7ca4f_Traceguids, v15);
  }
  LODWORD(v34) = 0;
  v10 = v35;
  v11 = 1;
  if ( v35 )
  {
    while ( *v7 )
    {
      if ( (unsigned int)MwszStringExist(v10, v7, v16) )
      {
        LODWORD(v34) = 1;
        v18 = 0;
        goto LABEL_35;
      }
      v17 = -1;
      do
        ++v17;
      while ( v7[v17] );
      v7 += v17 + 1;
    }
    v18 = 1168;
  }
  else
  {
    v18 = 87;
  }
LABEL_35:
  SetLastError(v18);
  v19 = *((unsigned int *)v8 + 5);
  v20 = 96 * v19;
  if ( !is_mul_ok(v19, 0x60u) )
    v20 = -1;
  v21 = __CFADD__(v20, 8);
  v22 = v20 + 8;
  if ( v21 )
    v22 = -1;
  v23 = (unsigned __int16 *)operator new[](v22, (const struct std::nothrow_t *)&std::nothrow);
  v35 = v23;
  if ( v23 )
  {
    *(_QWORD *)v23 = v19;
    v9 = (DynPlex *)(v23 + 4);
    `eh vector constructor iterator'(
      v23 + 4,
      0x60u,
      (unsigned int)v19,
      (void (*)(void *))DynPlex::DynPlex,
      (void (*)(void *))DynPlex::~DynPlex);
  }
  else
  {
    v9 = 0;
  }
  if ( !v9 )
  {
    v11 = 0;
    LastError = 14;
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_64;
    }
    v29 = 62;
    v30 = "pDynPlexList";
    v31 = 14;
    goto LABEL_63;
  }
  v24 = (struct _VM_PLEX_LAYOUT *)(v8 + 32);
  for ( i = 0; ; ++i )
  {
    if ( i >= *((_DWORD *)v8 + 5) )
    {
      LastError = 0;
      v27 = v38;
      *(_OWORD *)v38 = *(_OWORD *)v8;
      *((_OWORD *)v27 + 1) = *((_OWORD *)v8 + 1);
      *((_OWORD *)v27 + 2) = *((_OWORD *)v8 + 2);
      *((_OWORD *)v27 + 3) = *((_OWORD *)v8 + 3);
      *((_OWORD *)v27 + 4) = *((_OWORD *)v8 + 4);
      *((_OWORD *)v27 + 5) = *((_OWORD *)v8 + 5);
      *((_OWORD *)v27 + 6) = *((_OWORD *)v8 + 6);
      *((_DWORD *)v27 + 3) = -1;
      *((_DWORD *)v27 + 64) = *((_DWORD *)v8 + 5);
      *((_QWORD *)v27 + 33) = v9;
      v9 = 0;
      *((_OWORD *)v27 + 7) = *((_OWORD *)v8 + 1);
      *((_OWORD *)v27 + 8) = *((_OWORD *)v8 + 2);
      *((_OWORD *)v27 + 9) = *((_OWORD *)v8 + 3);
      *((_OWORD *)v27 + 10) = *((_OWORD *)v8 + 4);
      *((_OWORD *)v27 + 11) = *((_OWORD *)v8 + 5);
      *((_OWORD *)v27 + 12) = *((_OWORD *)v8 + 6);
      *((_DWORD *)v27 + 29) = 0;
      *((struct _GUID *)v27 + 14) = *v37;
      *((struct _GUID *)v27 + 13) = *v39;
      *((_QWORD *)v27 + 30) = v10;
      v10 = 0;
      *((_DWORD *)v27 + 68) = (_DWORD)v34;
      goto LABEL_64;
    }
    if ( !DynPlex::Initialize((DynPlex *)((char *)v9 + 96 * i), hDevice, v37, v24) )
      break;
    v24 = (struct _VM_PLEX_LAYOUT *)((char *)v24 + *(unsigned int *)v24);
  }
  v11 = 0;
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
  {
    v26 = GetLastError();
    WPP_SF_Dsd(
      *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
      63,
      (unsigned int)WPP_b771bf60a8233494a340a3d0d6c7ca4f_Traceguids,
      v26,
      (__int64)"GetLastError()",
      i);
  }
LABEL_64:
  CoTaskMemFree(v8);
  CoTaskMemFree(v10);
  if ( v9 )
    DynPlex::`vector deleting destructor'(v9, v32);
  TraceFunctionExit(L"DynVolume::Initialize");
  SetLastError(LastError);
  return v11;
}

```

## disassembly

```asm
0x1400d4088  push    rbp
0x1400d408a  push    rbx
0x1400d408b  push    rsi
0x1400d408c  push    rdi
0x1400d408d  push    r12
0x1400d408f  push    r13
0x1400d4091  push    r14
0x1400d4093  push    r15
0x1400d4095  lea     rbp, [rsp-17h]
0x1400d409a  sub     rsp, 0E8h
0x1400d40a1  mov     rax, cs:__security_cookie
0x1400d40a8  xor     rax, rsp
0x1400d40ab  mov     [rbp+4Fh+var_50], rax
0x1400d40af  mov     rsi, r9
0x1400d40b2  mov     [rbp+4Fh+var_C8], r9
0x1400d40b6  mov     r12, r8
0x1400d40b9  mov     [rsp+120h+var_D8], r8
0x1400d40be  mov     [rsp+120h+hDevice], rdx
0x1400d40c3  mov     [rsp+120h+var_D0], rcx
0x1400d40c8  mov     rdi, [rbp+4Fh+arg_20]
0x1400d40cc  lea     rcx, aDynvolumeIniti; "DynVolume::Initialize"
0x1400d40d3  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x1400d40d8  xorps   xmm0, xmm0
0x1400d40db  movups  [rbp+4Fh+InBuffer], xmm0
0x1400d40df  movups  [rbp+4Fh+var_B0], xmm0
0x1400d40e3  xor     ebx, ebx
0x1400d40e5  mov     r14d, ebx
0x1400d40e8  mov     [rsp+120h+var_F0], rbx
0x1400d40ed  mov     r15d, ebx
0x1400d40f0  mov     r13d, ebx
0x1400d40f3  mov     [rsp+120h+var_E8], rbx
0x1400d40f8  mov     [rbp+4Fh+var_A0], bx
0x1400d40fc  xor     edx, edx; Val
0x1400d40fe  lea     r8d, [rbx+48h]; Size
0x1400d4102  lea     rcx, [rbp+4Fh+var_9E]; void *
0x1400d4106  call    memset_0
0x1400d410b  test    r12, r12
0x1400d410e  jz      loc_1400D45D7
0x1400d4114  test    rsi, rsi
0x1400d4117  jz      loc_1400D45A6
0x1400d411d  test    rdi, rdi
0x1400d4120  jz      loc_1400D456D
0x1400d4126  lea     r8d, [rbx+25h]; unsigned int
0x1400d412a  lea     rdx, [rbp+4Fh+var_A0]; unsigned __int16 *
0x1400d412e  mov     rcx, rsi; struct _GUID *
0x1400d4131  call    ?SafeStrConvertGuidString@@YAHPEAU_GUID@@PEAGK@Z; SafeStrConvertGuidString(_GUID *,ushort *,ulong)
0x1400d4136  test    eax, eax
0x1400d4138  jnz     short loc_1400D418A
0x1400d413a  mov     esi, ebx
0x1400d413c  call    cs:__imp_GetLastError
0x1400d4142  mov     edi, eax
0x1400d4144  lea     rbx, WPP_GLOBAL_Control
0x1400d414b  mov     rax, cs:WPP_GLOBAL_Control
0x1400d4152  cmp     rax, rbx
0x1400d4155  jz      loc_1400D461B
0x1400d415b  test    byte ptr [rax+1Ch], 8
0x1400d415f  jz      loc_1400D461B
0x1400d4165  call    cs:__imp_GetLastError
0x1400d416b  lea     edx, [r13+38h]
0x1400d416f  lea     rcx, aSafestrconvert; "SafeStrConvertGuidString(pVolId, ARRAY_"...
0x1400d4176  mov     [rsp+120h+var_100], rcx
0x1400d417b  mov     r9d, eax
0x1400d417e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d4185  jmp     loc_1400D460B
0x1400d418a  lea     rbx, WPP_GLOBAL_Control
0x1400d4191  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d4198  cmp     rcx, rbx
0x1400d419b  jz      short loc_1400D41BC
0x1400d419d  test    byte ptr [rcx+1Ch], 2
0x1400d41a1  jz      short loc_1400D41BC
0x1400d41a3  mov     edx, 39h ; '9'
0x1400d41a8  lea     r9, [rbp+4Fh+var_A0]
0x1400d41ac  lea     r8, WPP_b771bf60a8233494a340a3d0d6c7ca4f_Traceguids
0x1400d41b3  mov     rcx, [rcx+10h]
0x1400d41b7  call    WPP_SF_S
0x1400d41bc  movups  xmm0, xmmword ptr [r12]
0x1400d41c1  movdqu  [rbp+4Fh+InBuffer], xmm0
0x1400d41c6  movups  xmm1, xmmword ptr [rsi]
0x1400d41c9  movdqu  [rbp+4Fh+var_B0], xmm1
0x1400d41ce  lea     rax, [rsp+120h+var_F0]
0x1400d41d3  mov     [rsp+120h+var_100], rax; void **
0x1400d41d8  mov     r9d, 20h ; ' '; nInBufferSize
0x1400d41de  lea     r8, [rbp+4Fh+InBuffer]; lpInBuffer
0x1400d41e2  mov     edx, 764338h; dwIoControlCode
0x1400d41e7  mov     rcx, [rsp+120h+hDevice]; hDevice
0x1400d41ec  call    ?DoIoctlCall@@YAHPEAXK0KPEAPEAX@Z; DoIoctlCall(void *,ulong,void *,ulong,void * *)
0x1400d41f1  xor     r12d, r12d
0x1400d41f4  test    eax, eax
0x1400d41f6  jnz     short loc_1400D4250
0x1400d41f8  mov     esi, r12d
0x1400d41fb  call    cs:__imp_GetLastError
0x1400d4201  mov     edi, eax
0x1400d4203  mov     rax, cs:WPP_GLOBAL_Control
0x1400d420a  cmp     rax, rbx
0x1400d420d  jz      short loc_1400D4246
0x1400d420f  test    byte ptr [rax+1Ch], 8
0x1400d4213  jz      short loc_1400D4246
0x1400d4215  call    cs:__imp_GetLastError
0x1400d421b  lea     edx, [r12+3Ah]
0x1400d4220  lea     rcx, aGetlasterror_1; "GetLastError()"
0x1400d4227  mov     [rsp+120h+var_100], rcx
0x1400d422c  mov     r9d, eax
0x1400d422f  lea     r8, WPP_b771bf60a8233494a340a3d0d6c7ca4f_Traceguids
0x1400d4236  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d423d  mov     rcx, [rcx+10h]
0x1400d4241  call    WPP_SF_Ds
0x1400d4246  mov     r14, [rsp+120h+var_F0]
0x1400d424b  jmp     loc_1400D461B
0x1400d4250  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d4257  cmp     rcx, rbx
0x1400d425a  jz      short loc_1400D4277
0x1400d425c  test    byte ptr [rcx+1Ch], 2
0x1400d4260  jz      short loc_1400D4277
0x1400d4262  mov     edx, 3Bh ; ';'
0x1400d4267  lea     r8, WPP_b771bf60a8233494a340a3d0d6c7ca4f_Traceguids
0x1400d426e  mov     rcx, [rcx+10h]
0x1400d4272  call    WPP_SF_
0x1400d4277  mov     rdx, rsi
0x1400d427a  mov     r14, [rsp+120h+var_F0]
0x1400d427f  mov     rcx, r14
0x1400d4282  call    TraceQueryVolumeInfoBuffer
0x1400d4287  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d428e  cmp     rcx, rbx
0x1400d4291  jz      short loc_1400D42AE
0x1400d4293  test    byte ptr [rcx+1Ch], 2
0x1400d4297  jz      short loc_1400D42AE
0x1400d4299  mov     edx, 3Ch ; '<'
0x1400d429e  lea     r8, WPP_b771bf60a8233494a340a3d0d6c7ca4f_Traceguids
0x1400d42a5  mov     rcx, [rcx+10h]
0x1400d42a9  call    WPP_SF_
0x1400d42ae  mov     esi, [r14+0Ch]
0x1400d42b2  add     rsi, r14
0x1400d42b5  lea     rdx, [rsp+120h+var_E8]; unsigned __int16 **
0x1400d42ba  mov     rcx, rsi; unsigned __int16 *
0x1400d42bd  call    ?MtMgrGetSymbolicNames@@YAHPEBGPEAPEAG@Z; MtMgrGetSymbolicNames(ushort const *,ushort * *)
0x1400d42c2  test    eax, eax
0x1400d42c4  jnz     short loc_1400D42EE
0x1400d42c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d42cd  cmp     rcx, rbx
0x1400d42d0  jz      short loc_1400D42EE
0x1400d42d2  test    byte ptr [rcx+1Ch], 2
0x1400d42d6  jz      short loc_1400D42EE
0x1400d42d8  lea     edx, [rax+3Dh]
0x1400d42db  mov     r9, rsi
0x1400d42de  lea     r8, WPP_b771bf60a8233494a340a3d0d6c7ca4f_Traceguids
0x1400d42e5  mov     rcx, [rcx+10h]
0x1400d42e9  call    WPP_SF_S
0x1400d42ee  mov     dword ptr [rsp+120h+var_F0], r12d
0x1400d42f3  mov     r13, [rsp+120h+var_E8]
0x1400d42f8  mov     esi, 1
0x1400d42fd  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400d4301  test    r13, r13
0x1400d4304  jz      short loc_1400D4341
0x1400d4306  cmp     [rdi], r12w
0x1400d430a  jz      short loc_1400D433A
0x1400d430c  mov     rdx, rdi; unsigned __int16 *
0x1400d430f  mov     rcx, r13; unsigned __int16 *
0x1400d4312  call    ?MwszStringExist@@YAHPEAG0H@Z; MwszStringExist(ushort *,ushort *,int)
0x1400d4317  test    eax, eax
0x1400d4319  jnz     short loc_1400D4332
0x1400d431b  mov     rax, r15
0x1400d431e  inc     rax
0x1400d4321  cmp     [rdi+rax*2], r12w
0x1400d4326  jnz     short loc_1400D431E
0x1400d4328  lea     rdi, [rdi+rax*2]
0x1400d432c  add     rdi, 2
0x1400d4330  jmp     short loc_1400D4306
0x1400d4332  mov     dword ptr [rsp+120h+var_F0], esi
0x1400d4336  xor     ecx, ecx
0x1400d4338  jmp     short loc_1400D4346
0x1400d433a  mov     ecx, 490h
0x1400d433f  jmp     short loc_1400D4346
0x1400d4341  mov     ecx, 57h ; 'W'; dwErrCode
0x1400d4346  call    cs:__imp_SetLastError
0x1400d434c  mov     edi, [r14+14h]
0x1400d4350  mov     r12d, 60h ; '`'
0x1400d4356  mov     eax, r12d
0x1400d4359  mul     rdi
0x1400d435c  cmovb   rax, r15
0x1400d4360  add     rax, 8
0x1400d4364  cmovb   rax, r15
0x1400d4368  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400d436f  mov     rcx, rax; unsigned __int64
0x1400d4372  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400d4377  mov     [rsp+120h+var_E8], rax
0x1400d437c  xor     edx, edx
0x1400d437e  test    rax, rax
0x1400d4381  jz      short loc_1400D43AF
0x1400d4383  mov     [rax], rdi
0x1400d4386  lea     r15, [rax+8]
0x1400d438a  lea     rax, ??1DynPlex@@QEAA@XZ; DynPlex::~DynPlex(void)
0x1400d4391  mov     [rsp+120h+var_100], rax; void (*)(void *)
0x1400d4396  lea     r9, ??0DynPlex@@QEAA@XZ; void (*)(void *)
0x1400d439d  mov     r8d, edi; unsigned __int64
0x1400d43a0  mov     edx, r12d; unsigned __int64
0x1400d43a3  mov     rcx, r15; void *
0x1400d43a6  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1400d43ab  xor     edx, edx
0x1400d43ad  jmp     short loc_1400D43B2
0x1400d43af  mov     r15, rdx
0x1400d43b2  test    r15, r15
0x1400d43b5  jz      loc_1400D453A
0x1400d43bb  lea     rdi, [r14+20h]
0x1400d43bf  mov     r12d, edx
0x1400d43c2  cmp     r12d, [r14+14h]
0x1400d43c6  jnb     loc_1400D445B
0x1400d43cc  mov     eax, r12d
0x1400d43cf  lea     rcx, [rax+rax*2]
0x1400d43d3  shl     rcx, 5
0x1400d43d7  add     rcx, r15; this
0x1400d43da  mov     r9, rdi; struct _VM_PLEX_LAYOUT *
0x1400d43dd  mov     r8, [rsp+120h+var_D8]; struct _GUID *
0x1400d43e2  mov     rdx, [rsp+120h+hDevice]; void *
0x1400d43e7  call    ?Initialize@DynPlex@@QEAAHPEAXPEAU_GUID@@PEAU_VM_PLEX_LAYOUT@@@Z; DynPlex::Initialize(void *,_GUID *,_VM_PLEX_LAYOUT *)
0x1400d43ec  xor     edx, edx
0x1400d43ee  test    eax, eax
0x1400d43f0  jz      short loc_1400D43FC
0x1400d43f2  mov     eax, [rdi]
0x1400d43f4  add     rdi, rax
0x1400d43f7  add     r12d, esi
0x1400d43fa  jmp     short loc_1400D43C2
0x1400d43fc  mov     esi, edx
0x1400d43fe  call    cs:__imp_GetLastError
0x1400d4404  mov     edi, eax
0x1400d4406  mov     rax, cs:WPP_GLOBAL_Control
0x1400d440d  cmp     rax, rbx
0x1400d4410  jz      loc_1400D461B
0x1400d4416  test    byte ptr [rax+1Ch], 8
0x1400d441a  jz      loc_1400D461B
0x1400d4420  call    cs:__imp_GetLastError
0x1400d4426  mov     edx, 3Fh ; '?'
0x1400d442b  mov     [rsp+120h+var_F8], r12d
0x1400d4430  lea     rcx, aGetlasterror_1; "GetLastError()"
0x1400d4437  mov     [rsp+120h+var_100], rcx
0x1400d443c  mov     r9d, eax
0x1400d443f  lea     r8, WPP_b771bf60a8233494a340a3d0d6c7ca4f_Traceguids
0x1400d4446  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d444d  mov     rcx, [rcx+10h]
0x1400d4451  call    WPP_SF_Dsd
0x1400d4456  jmp     loc_1400D461B
0x1400d445b  mov     edi, edx
0x1400d445d  movups  xmm0, xmmword ptr [r14]
0x1400d4461  mov     rcx, [rsp+120h+var_D0]
0x1400d4466  movups  xmmword ptr [rcx], xmm0
0x1400d4469  movups  xmm1, xmmword ptr [r14+10h]
0x1400d446e  movups  xmmword ptr [rcx+10h], xmm1
0x1400d4472  movups  xmm0, xmmword ptr [r14+20h]
0x1400d4477  movups  xmmword ptr [rcx+20h], xmm0
0x1400d447b  movups  xmm1, xmmword ptr [r14+30h]
0x1400d4480  movups  xmmword ptr [rcx+30h], xmm1
0x1400d4484  movups  xmm0, xmmword ptr [r14+40h]
0x1400d4489  movups  xmmword ptr [rcx+40h], xmm0
0x1400d448d  movups  xmm1, xmmword ptr [r14+50h]
0x1400d4492  movups  xmmword ptr [rcx+50h], xmm1
0x1400d4496  movups  xmm0, xmmword ptr [r14+60h]
0x1400d449b  movups  xmmword ptr [rcx+60h], xmm0
0x1400d449f  mov     dword ptr [rcx+0Ch], 0FFFFFFFFh
0x1400d44a6  mov     eax, [r14+14h]
0x1400d44aa  mov     [rcx+100h], eax
0x1400d44b0  mov     [rcx+108h], r15
0x1400d44b7  mov     r15, rdx
0x1400d44ba  movups  xmm0, xmmword ptr [r14+10h]
0x1400d44bf  movups  xmmword ptr [rcx+70h], xmm0
0x1400d44c3  movups  xmm1, xmmword ptr [r14+20h]
0x1400d44c8  movups  xmmword ptr [rcx+80h], xmm1
0x1400d44cf  movups  xmm0, xmmword ptr [r14+30h]
0x1400d44d4  movups  xmmword ptr [rcx+90h], xmm0
0x1400d44db  movups  xmm1, xmmword ptr [r14+40h]
0x1400d44e0  movups  xmmword ptr [rcx+0A0h], xmm1
0x1400d44e7  movups  xmm0, xmmword ptr [r14+50h]
0x1400d44ec  movups  xmmword ptr [rcx+0B0h], xmm0
0x1400d44f3  movups  xmm1, xmmword ptr [r14+60h]
0x1400d44f8  movups  xmmword ptr [rcx+0C0h], xmm1
0x1400d44ff  mov     [rcx+74h], edx
0x1400d4502  mov     rax, [rsp+120h+var_D8]
0x1400d4507  movups  xmm0, xmmword ptr [rax]
0x1400d450a  movdqu  xmmword ptr [rcx+0E0h], xmm0
0x1400d4512  mov     rax, [rbp+4Fh+var_C8]
0x1400d4516  movups  xmm1, xmmword ptr [rax]
0x1400d4519  movdqu  xmmword ptr [rcx+0D0h], xmm1
0x1400d4521  mov     [rcx+0F0h], r13
0x1400d4528  mov     r13, rdx
0x1400d452b  mov     eax, dword ptr [rsp+120h+var_F0]
0x1400d452f  mov     [rcx+110h], eax
0x1400d4535  jmp     loc_1400D461B
0x1400d453a  mov     esi, edx
0x1400d453c  mov     edi, 0Eh
0x1400d4541  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d4548  cmp     rcx, rbx
0x1400d454b  jz      loc_1400D461B
0x1400d4551  test    byte ptr [rcx+1Ch], 8
0x1400d4555  jz      loc_1400D461B
0x1400d455b  lea     edx, [rdi+30h]
0x1400d455e  lea     rax, aPdynplexlist; "pDynPlexList"
0x1400d4565  mov     r9d, edi
0x1400d4568  jmp     loc_1400D4606
0x1400d456d  mov     esi, ebx
0x1400d456f  mov     r9d, 57h ; 'W'
0x1400d4575  mov     edi, r9d
0x1400d4578  lea     rbx, WPP_GLOBAL_Control
  ... truncated ...
```
