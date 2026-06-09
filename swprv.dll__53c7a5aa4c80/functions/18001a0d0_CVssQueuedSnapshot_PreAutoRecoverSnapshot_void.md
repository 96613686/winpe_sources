# CVssQueuedSnapshot::PreAutoRecoverSnapshot(void)

- ea: `0x18001a0d0`
- end: `0x18001a5ee`
- name: `?PreAutoRecoverSnapshot@CVssQueuedSnapshot@@QEAAXXZ`
- size: `1310`
- prototype: `void __fastcall(CVssQueuedSnapshot *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800144a0`

## callees

- `0x180001580`
- `0x18000212c`
- `0x180002cfc`
- `0x1800036e8`
- `0x1800039d8`
- `0x180003de8`
- `0x180004b10`
- `0x18000610c`
- `0x180018d0c`
- `0x180019458`
- `0x18001a0d0`
- `0x18001a940`
- `0x18001d23c`
- `0x180033a8c`
- `0x180033c78`
- `0x18003649c`
- `0x1800367b8`
- `0x180037080`
- `0x180037e24`
- `0x180039718`
- `0x18003a05c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18001a2c7`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18001a2c7`

## string_xrefs

- `0x18001a1cb`: `The snapshot was deleted before PreFinalCommit`
- `0x18001a5d3`: `CVssIOCTLChannel::Open failed with hr: %#x`
- `0x18001a23d`: `SYSTEM\CurrentControlSet\Services\VSS\Settings`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CVssQueuedSnapshot::PreAutoRecoverSnapshot(CVssQueuedSnapshot *this)
{
  struct _VSS_SNAPSHOT_PROP *SnapshotProperties; // rsi
  char v3; // r9
  char v4; // di
  WCHAR *v5; // rax
  int v6; // ecx
  int v7; // edx
  WCHAR *v8; // rax
  int v9; // ecx
  int v10; // edx
  struct _VSS_SNAPSHOT_PROP *v11; // rax
  unsigned int v12; // edi
  unsigned int v13; // edi
  unsigned int v14; // edi
  LPDWORD lpMaximumComponentLength; // [rsp+20h] [rbp-E0h]
  LPDWORD lpMaximumComponentLengtha; // [rsp+20h] [rbp-E0h]
  __int64 nFileSystemNameSize; // [rsp+38h] [rbp-C8h]
  _BYTE v18[8]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v19; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID m_SnapshotId; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 *v21; // [rsp+70h] [rbp-90h] BYREF
  __int128 v22; // [rsp+78h] [rbp-88h]
  __int128 v23; // [rsp+88h] [rbp-78h]
  _WORD v24[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v25; // [rsp+9Ch] [rbp-64h]
  __int64 v26; // [rsp+A8h] [rbp-58h]
  __int64 v27; // [rsp+B0h] [rbp-50h]
  int v28; // [rsp+B8h] [rbp-48h]
  __int64 v29; // [rsp+C0h] [rbp-40h]
  __int16 v30; // [rsp+C8h] [rbp-38h]
  void **v31; // [rsp+D0h] [rbp-30h]
  __int64 v32; // [rsp+D8h] [rbp-28h]
  int v33; // [rsp+110h] [rbp+10h]
  HKEY v34[4]; // [rsp+120h] [rbp+20h] BYREF
  const unsigned __int16 *v35; // [rsp+140h] [rbp+40h] BYREF
  const wchar_t *v36; // [rsp+148h] [rbp+48h]
  const unsigned __int16 *v37; // [rsp+150h] [rbp+50h]
  int v38; // [rsp+158h] [rbp+58h]
  int v39; // [rsp+15Ch] [rbp+5Ch]
  int v40; // [rsp+160h] [rbp+60h]
  _BYTE v41[120]; // [rsp+168h] [rbp+68h] BYREF
  int v42; // [rsp+1E0h] [rbp+E0h]
  LPVOID v43; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v44; // [rsp+1F8h] [rbp+F8h]
  WCHAR FileSystemNameBuffer[264]; // [rsp+260h] [rbp+160h] BYREF

  v21 = L"base\\stor\\vss\\modules\\softprv\\src\\qsnap.cxx";
  *(_QWORD *)&v22 = L"CVssQueuedSnapshot::PreAutoRecoverSnapshot";
  *((_QWORD *)&v22 + 1) = L"SPRQSNPC";
  *(_QWORD *)&v23 = 0x200000134LL;
  DWORD2(v23) = 255;
  v33 = 0x1000000;
  memset_0(v24, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v43, (__int64)&v21, 0);
  SnapshotProperties = CVssQueuedSnapshot::GetSnapshotProperties(this);
  m_SnapshotId = SnapshotProperties->m_SnapshotId;
  if ( !CVssQueuedSnapshot::FindPersistedSnapshotByID(
          &m_SnapshotId,
          *((_DWORD *)this + 70),
          &SnapshotProperties->m_pwszSnapshotDeviceObject) )
  {
    v21 = L"base\\stor\\vss\\modules\\softprv\\src\\qsnap.cxx";
    *(_QWORD *)&v22 = L"CVssQueuedSnapshot::PreAutoRecoverSnapshot";
    *((_QWORD *)&v22 + 1) = L"SPRQSNPC";
    *(_QWORD *)&v23 = 0x20000013CLL;
    DWORD2(v23) = 255;
    v33 = 0x1000000;
    memset_0(v24, 0, 0x78u);
    CVssFunctionTracer::Throw(
      (CVssFunctionTracer *)&v43,
      (const struct CVssDebugInfo *)&v21,
      -2147212538,
      L"The snapshot was deleted before PreFinalCommit");
  }
  if ( !*((_BYTE *)this + 258) )
  {
    v34[3] = 0;
    v34[2] = (HKEY)&CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
    v34[1] = 0;
    v34[0] = (HKEY)1;
    if ( !CVssRegistryKey::Open(
            (REGSAM *)v34,
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Services\\VSS\\Settings")
      || (v19 = 0, !CVssRegistryKey::GetValue(v34, L"DisableAutoRecovery", &v19, v3))
      || !v19 )
    {
      memset_0(FileSystemNameBuffer, 0, 0x20Au);
      v4 = 0;
      v18[0] = 0;
      if ( GetVolumeInformationW(
             SnapshotProperties->m_pwszOriginalVolumeName,
             0,
             0,
             0,
             0,
             0,
             FileSystemNameBuffer,
             0x104u) )
      {
        v5 = FileSystemNameBuffer;
        do
        {
          v6 = *(WCHAR *)((char *)v5 + (char *)L"NTFS" - (char *)FileSystemNameBuffer);
          v7 = *v5 - v6;
          if ( v7 )
            break;
          ++v5;
        }
        while ( v6 );
        if ( !v7 )
          goto LABEL_18;
        v8 = FileSystemNameBuffer;
        do
        {
          v9 = *(WCHAR *)((char *)v8 + (char *)L"ReFS" - (char *)FileSystemNameBuffer);
          v10 = *v8 - v9;
          if ( v10 )
            break;
          ++v8;
        }
        while ( v9 );
        if ( !v10 )
        {
LABEL_18:
          *(_QWORD *)m_SnapshotId.Data4 = 0;
          *(_QWORD *)&m_SnapshotId.Data1 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
          v11 = CVssQueuedSnapshot::GetSnapshotProperties(this);
          CVssAutoString<CVssAutoLocalPtr<unsigned short *>>::CopyFrom(
            (__int64)&m_SnapshotId,
            v11->m_pwszSnapshotDeviceObject);
          CVssAutoString<CVssAutoLocalPtr<unsigned short *>>::Append(&m_SnapshotId);
          v21 = 0;
          v24[0] = 0;
          v25 = 0;
          v26 = 0;
          v27 = 0;
          v28 = 0;
          v29 = 0;
          v30 = 0;
          v32 = 0;
          v31 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
          v22 = 0;
          v23 = 0;
          CVssIOCTLChannel::Open(
            (CVssIOCTLChannel *)&v21,
            (__int64)&v43,
            *(unsigned __int16 **)m_SnapshotId.Data4,
            0,
            1,
            2,
            0x80000000,
            nFileSystemNameSize,
            0x2000000u);
          v12 = v44;
          if ( (int)v44 < 0 )
          {
            v35 = L"base\\stor\\vss\\modules\\softprv\\src\\qsnap.cxx";
            v36 = L"CVssQueuedSnapshot::PreAutoRecoverSnapshot";
            v37 = L"SPRQSNPC";
            v38 = 361;
            v39 = 2;
            v40 = 255;
            v42 = 0x1000000;
            memset_0(v41, 0, sizeof(v41));
            LODWORD(lpMaximumComponentLength) = v12;
            CVssFunctionTracer::TranslateGenericError(
              &v43,
              &v35,
              v12,
              L"CVssIOCTLChannel::Open failed with hr: %#x",
              lpMaximumComponentLength);
          }
          CVssIOCTLChannel::Call(&v21, (__int64)&v43, 0x9418Cu, 1, 0, 0);
          v13 = v44;
          if ( (int)v44 < 0 )
          {
            v35 = L"base\\stor\\vss\\modules\\softprv\\src\\qsnap.cxx";
            v36 = L"CVssQueuedSnapshot::PreAutoRecoverSnapshot";
            v37 = L"SPRQSNPC";
            v38 = 367;
            v39 = 2;
            v40 = 255;
            v42 = 0x1000000;
            memset_0(v41, 0, sizeof(v41));
            LODWORD(lpMaximumComponentLengtha) = v13;
            CVssFunctionTracer::TranslateGenericError(
              &v43,
              &v35,
              v13,
              L"CVssIOCTLChannel::Call(FSCTL_TXFS_TRANSACTION_ACTIVE) failed with hr: %#x",
              lpMaximumComponentLengtha);
          }
          CVssIOCTLChannel::Unpack<unsigned char>((CVssIOCTLChannel *)&v21, (struct CVssFunctionTracer *)&v43, v18);
          v14 = v44;
          if ( (int)v44 < 0 )
          {
            v35 = L"base\\stor\\vss\\modules\\softprv\\src\\qsnap.cxx";
            v36 = L"CVssQueuedSnapshot::PreAutoRecoverSnapshot";
            v37 = L"SPRQSNPC";
            v38 = 373;
            v39 = 2;
            v40 = 255;
            v42 = 0x1000000;
            memset_0(v41, 0, sizeof(v41));
            LODWORD(lpMaximumComponentLengtha) = v14;
            CVssFunctionTracer::TranslateGenericError(
              &v43,
              &v35,
              v14,
              L"CVssIOCTLChannel::Unpack failed with hr: %#x",
              lpMaximumComponentLengtha);
          }
          CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v21);
          CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&void * LocalFree(void *),void * (*)(unsigned __int64),&void * LocalAllocate(unsigned __int64)>>::~CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&void * LocalFree(void *),void * (*)(unsigned __int64),&void * LocalAllocate(unsigned __int64)>>(&m_SnapshotId);
          v4 = v18[0];
        }
      }
      else
      {
        v21 = L"base\\stor\\vss\\modules\\softprv\\src\\qsnap.cxx";
        *(_QWORD *)&v22 = L"CVssQueuedSnapshot::PreAutoRecoverSnapshot";
        *((_QWORD *)&v22 + 1) = L"SPRQSNPC";
        *(_QWORD *)&v23 = 0x200000151LL;
        DWORD2(v23) = 255;
        v33 = 0x1000000;
        memset_0(v24, 0, 0x78u);
        CVssFunctionTracer::Trace(
          &v43,
          &v21,
          L"GetVolumeInformation(%s) fails. Assume non-NTFS.",
          SnapshotProperties->m_pwszOriginalVolumeName);
      }
      if ( (*((_DWORD *)this + 70) & 0x400000) != 0 || v4 )
      {
        CVssQueuedSnapshot::SetAutoRecoverAttribute(this);
        *((_BYTE *)this + 257) = 1;
      }
    }
    CVssRegistryKey::~CVssRegistryKey((CVssRegistryKey *)v34);
  }
  CVssFunctionTracer::~CVssFunctionTracer(&v43);
}

```

## disassembly

```asm
0x18001a0d0  push    rbp
0x18001a0d2  push    rbx
0x18001a0d3  push    rsi
0x18001a0d4  push    rdi
0x18001a0d5  push    r12
0x18001a0d7  push    r13
0x18001a0d9  push    r14
0x18001a0db  push    r15
0x18001a0dd  lea     rbp, [rsp-388h]
0x18001a0e5  sub     rsp, 488h
0x18001a0ec  mov     rax, cs:__security_cookie
0x18001a0f3  xor     rax, rsp
0x18001a0f6  mov     [rbp+3C0h+var_50], rax
0x18001a0fd  mov     rbx, rcx
0x18001a100  lea     r12, aBaseStorVssMod_18; "base\\stor\\vss\\modules\\softprv\\src"...
0x18001a107  mov     [rsp+4C0h+var_450], r12
0x18001a10c  lea     r13, aCvssqueuedsnap_2; "CVssQueuedSnapshot::PreAutoRecoverSnaps"...
0x18001a113  mov     qword ptr [rsp+4C0h+var_448], r13
0x18001a118  lea     rdi, aSprqsnpc; "SPRQSNPC"
0x18001a11f  mov     qword ptr [rbp+3C0h+var_448+8], rdi
0x18001a123  mov     dword ptr [rbp+3C0h+var_438], 134h
0x18001a12a  mov     r15d, 2
0x18001a130  mov     dword ptr [rbp+3C0h+var_438+4], r15d
0x18001a134  mov     dword ptr [rbp+3C0h+var_438+8], 0FFh
0x18001a13b  xor     r14d, r14d
0x18001a13e  mov     [rbp+3C0h+var_3B0], 1000000h
0x18001a145  xor     edx, edx; Val
0x18001a147  lea     r8d, [r15+76h]; Size
0x18001a14b  lea     rcx, [rbp+3C0h+var_428]; void *
0x18001a14f  call    memset_0
0x18001a154  xor     r8d, r8d
0x18001a157  lea     rdx, [rsp+4C0h+var_450]
0x18001a15c  lea     rcx, [rbp+3C0h+var_2D0]
0x18001a163  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18001a168  nop
0x18001a169  mov     rcx, rbx; this
0x18001a16c  call    ?GetSnapshotProperties@CVssQueuedSnapshot@@QEAAPEAU_VSS_SNAPSHOT_PROP@@XZ; CVssQueuedSnapshot::GetSnapshotProperties(void)
0x18001a171  mov     rsi, rax
0x18001a174  movups  xmm0, xmmword ptr [rax]
0x18001a177  movdqu  xmmword ptr [rsp+4C0h+var_460.Data1], xmm0
0x18001a17d  lea     r8, [rax+28h]; unsigned __int16 **
0x18001a181  mov     edx, [rbx+118h]; int
0x18001a187  lea     rcx, [rsp+4C0h+var_460]; struct _GUID
0x18001a18c  call    ?FindPersistedSnapshotByID@CVssQueuedSnapshot@@SA_NU_GUID@@JPEAPEAG@Z; CVssQueuedSnapshot::FindPersistedSnapshotByID(_GUID,long,ushort * *)
0x18001a191  test    al, al
0x18001a193  jnz     short loc_18001A1EA
0x18001a195  mov     [rsp+4C0h+var_450], r12
0x18001a19a  mov     qword ptr [rsp+4C0h+var_448], r13
0x18001a19f  mov     qword ptr [rbp+3C0h+var_448+8], rdi
0x18001a1a3  mov     dword ptr [rbp+3C0h+var_438], 13Ch
0x18001a1aa  mov     dword ptr [rbp+3C0h+var_438+4], r15d
0x18001a1ae  mov     dword ptr [rbp+3C0h+var_438+8], 0FFh
0x18001a1b5  mov     [rbp+3C0h+var_3B0], 1000000h
0x18001a1bc  xor     edx, edx; Val
0x18001a1be  lea     r8d, [r15+76h]; Size
0x18001a1c2  lea     rcx, [rbp+3C0h+var_428]; void *
0x18001a1c6  call    memset_0
0x18001a1cb  lea     r9, aTheSnapshotWas; "The snapshot was deleted before PreFina"...
0x18001a1d2  mov     r8d, 80042306h
0x18001a1d8  lea     rdx, [rsp+4C0h+var_450]
0x18001a1dd  lea     rcx, [rbp+3C0h+var_2D0]
0x18001a1e4  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18001a1ea  cmp     [rbx+102h], r14b
0x18001a1f1  jz      short loc_18001A222
0x18001a1f3  lea     rcx, [rbp+3C0h+var_2D0]; this
0x18001a1fa  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18001a1ff  mov     rcx, [rbp+3C0h+var_50]
0x18001a206  xor     rcx, rsp; StackCookie
0x18001a209  call    __security_check_cookie
0x18001a20e  add     rsp, 488h
0x18001a215  pop     r15
0x18001a217  pop     r14
0x18001a219  pop     r13
0x18001a21b  pop     r12
0x18001a21d  pop     rdi
0x18001a21e  pop     rsi
0x18001a21f  pop     rbx
0x18001a220  pop     rbp
0x18001a221  retn
0x18001a222  mov     [rbp+3C0h+var_388], r14
0x18001a226  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x18001a22d  mov     [rbp+3C0h+var_390], rax
0x18001a231  mov     [rbp+3C0h+var_398], r14
0x18001a235  mov     [rbp+3C0h+var_3A0], 1
0x18001a23d  lea     r8, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\VS"...
0x18001a244  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18001a24b  lea     rcx, [rbp+3C0h+var_3A0]; this
0x18001a24f  call    ?Open@CVssRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CVssRegistryKey::Open(HKEY__ *,ushort const *,...)
0x18001a254  test    al, al
0x18001a256  jz      short loc_18001A281
0x18001a258  mov     [rsp+4C0h+var_468], r14d
0x18001a25d  lea     r8, [rsp+4C0h+var_468]; unsigned int *
0x18001a262  lea     rdx, aDisableautorec; "DisableAutoRecovery"
0x18001a269  lea     rcx, [rbp+3C0h+var_3A0]; this
0x18001a26d  call    ?GetValue@CVssRegistryKey@@QEAA_NPEBGAEAK_N@Z; CVssRegistryKey::GetValue(ushort const *,ulong &,bool)
0x18001a272  test    al, al
0x18001a274  jz      short loc_18001A281
0x18001a276  cmp     [rsp+4C0h+var_468], r14d
0x18001a27b  jnz     loc_18001A4C9
0x18001a281  xor     edx, edx; Val
0x18001a283  mov     r8d, 20Ah; Size
0x18001a289  lea     rcx, [rbp+3C0h+FileSystemNameBuffer]; void *
0x18001a290  call    memset_0
0x18001a295  mov     dil, r14b
0x18001a298  mov     [rsp+4C0h+var_470], r14b
0x18001a29d  mov     dword ptr [rsp+4C0h+nFileSystemNameSize], 104h; nFileSystemNameSize
0x18001a2a5  lea     rax, [rbp+3C0h+FileSystemNameBuffer]
0x18001a2ac  mov     [rsp+4C0h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x18001a2b1  mov     [rsp+4C0h+lpFileSystemFlags], r14; lpFileSystemFlags
0x18001a2b6  mov     [rsp+4C0h+lpMaximumComponentLength], r14; lpMaximumComponentLength
0x18001a2bb  xor     r9d, r9d; lpVolumeSerialNumber
0x18001a2be  xor     r8d, r8d; nVolumeNameSize
0x18001a2c1  xor     edx, edx; lpVolumeNameBuffer
0x18001a2c3  mov     rcx, [rsi+30h]; lpRootPathName
0x18001a2c7  call    cs:__imp_GetVolumeInformationW
0x18001a2cd  test    eax, eax
0x18001a2cf  jnz     short loc_18001A32F
0x18001a2d1  mov     [rsp+4C0h+var_450], r12
0x18001a2d6  mov     qword ptr [rsp+4C0h+var_448], r13
0x18001a2db  lea     rax, aSprqsnpc; "SPRQSNPC"
0x18001a2e2  mov     qword ptr [rbp+3C0h+var_448+8], rax
0x18001a2e6  mov     dword ptr [rbp+3C0h+var_438], 151h
0x18001a2ed  mov     dword ptr [rbp+3C0h+var_438+4], r15d
0x18001a2f1  mov     dword ptr [rbp+3C0h+var_438+8], 0FFh
0x18001a2f8  mov     [rbp+3C0h+var_3B0], 1000000h
0x18001a2ff  xor     edx, edx; Val
0x18001a301  lea     r8d, [rdx+78h]; Size
0x18001a305  lea     rcx, [rbp+3C0h+var_428]; void *
0x18001a309  call    memset_0
0x18001a30e  mov     r9, [rsi+30h]
0x18001a312  lea     r8, aGetvolumeinfor; "GetVolumeInformation(%s) fails. Assume "...
0x18001a319  lea     rdx, [rsp+4C0h+var_450]
0x18001a31e  lea     rcx, [rbp+3C0h+var_2D0]
0x18001a325  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18001a32a  jmp     loc_18001A4A7
0x18001a32f  lea     rax, [rbp+3C0h+FileSystemNameBuffer]
0x18001a336  lea     r8, aNtfs_0; "NTFS"
0x18001a33d  sub     r8, rax
0x18001a340  movzx   edx, word ptr [rax]
0x18001a343  movzx   ecx, word ptr [rax+r8]
0x18001a348  sub     edx, ecx
0x18001a34a  jnz     short loc_18001A353
0x18001a34c  add     rax, r15
0x18001a34f  test    ecx, ecx
0x18001a351  jnz     short loc_18001A340
0x18001a353  test    edx, edx
0x18001a355  jz      short loc_18001A383
0x18001a357  lea     rax, [rbp+3C0h+FileSystemNameBuffer]
0x18001a35e  lea     r8, aRefs_0; "ReFS"
0x18001a365  sub     r8, rax
0x18001a368  movzx   edx, word ptr [rax]
0x18001a36b  movzx   ecx, word ptr [rax+r8]
0x18001a370  sub     edx, ecx
0x18001a372  jnz     short loc_18001A37B
0x18001a374  add     rax, r15
0x18001a377  test    ecx, ecx
0x18001a379  jnz     short loc_18001A368
0x18001a37b  test    edx, edx
0x18001a37d  jnz     loc_18001A4A7
0x18001a383  mov     qword ptr [rsp+4C0h+var_460.Data4], r14
0x18001a388  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x18001a38f  mov     qword ptr [rsp+4C0h+var_460.Data1], rax
0x18001a394  mov     rcx, rbx; this
0x18001a397  call    ?GetSnapshotProperties@CVssQueuedSnapshot@@QEAAPEAU_VSS_SNAPSHOT_PROP@@XZ; CVssQueuedSnapshot::GetSnapshotProperties(void)
0x18001a39c  mov     rdx, [rax+28h]
0x18001a3a0  lea     rcx, [rsp+4C0h+var_460]
0x18001a3a5  call    ?CopyFrom@?$CVssAutoString@V?$CVssAutoLocalPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoLocalPtr<ushort *>>::CopyFrom(ushort const *)
0x18001a3aa  lea     rcx, [rsp+4C0h+var_460]
0x18001a3af  call    ?Append@?$CVssAutoString@V?$CVssAutoLocalPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoLocalPtr<ushort *>>::Append(ushort const *)
0x18001a3b4  mov     [rsp+4C0h+var_450], r14
0x18001a3b9  mov     [rbp+3C0h+var_428], r14w
0x18001a3be  mov     [rbp+3C0h+var_424], r14
0x18001a3c2  mov     [rbp+3C0h+var_418], r14
0x18001a3c6  mov     [rbp+3C0h+var_410], r14
0x18001a3ca  mov     [rbp+3C0h+var_408], r14d
0x18001a3ce  mov     [rbp+3C0h+var_400], r14
0x18001a3d2  mov     [rbp+3C0h+var_3F8], r14w
0x18001a3d7  mov     [rbp+3C0h+var_3E8], r14
0x18001a3db  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x18001a3e2  mov     [rbp+3C0h+var_3F0], rax
0x18001a3e6  xorps   xmm0, xmm0
0x18001a3e9  movups  [rsp+4C0h+var_448], xmm0
0x18001a3ee  movups  [rbp+3C0h+var_438], xmm0
0x18001a3f2  mov     [rsp+4C0h+var_480], 2000000h
0x18001a3fa  mov     dword ptr [rsp+4C0h+lpFileSystemNameBuffer], 80000000h
0x18001a402  mov     dword ptr [rsp+4C0h+lpFileSystemFlags], r15d
0x18001a407  mov     byte ptr [rsp+4C0h+lpMaximumComponentLength], 1
0x18001a40c  xor     r9d, r9d
0x18001a40f  mov     r8, qword ptr [rsp+4C0h+var_460.Data4]
0x18001a414  lea     rdx, [rbp+3C0h+var_2D0]
0x18001a41b  lea     rcx, [rsp+4C0h+var_450]
0x18001a420  call    ?Open@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@PEBG_N2W4_VSS_ICHANNEL_LOGGING@@KKK@Z; CVssIOCTLChannel::Open(CVssFunctionTracer &,ushort const *,bool,bool,_VSS_ICHANNEL_LOGGING,ulong,ulong,ulong)
0x18001a425  mov     rdi, [rbp+3C0h+var_2C8]
0x18001a42c  test    edi, edi
0x18001a42e  js      loc_18001A591
0x18001a434  mov     [rsp+4C0h+lpFileSystemNameBuffer], r14
0x18001a439  mov     byte ptr [rsp+4C0h+lpFileSystemFlags], r14b
0x18001a43e  mov     dword ptr [rsp+4C0h+lpMaximumComponentLength], r14d
0x18001a443  mov     r9b, 1
0x18001a446  mov     r8d, 9418Ch
0x18001a44c  lea     rdx, [rbp+3C0h+var_2D0]
0x18001a453  lea     rcx, [rsp+4C0h+var_450]
0x18001a458  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x18001a45d  mov     rdi, [rbp+3C0h+var_2C8]
0x18001a464  test    edi, edi
0x18001a466  js      loc_18001A534
0x18001a46c  lea     r8, [rsp+4C0h+var_470]
0x18001a471  lea     rdx, [rbp+3C0h+var_2D0]
0x18001a478  lea     rcx, [rsp+4C0h+var_450]
0x18001a47d  call    ??$Unpack@E@CVssIOCTLChannel@@QEAAXAEAVCVssFunctionTracer@@PEAEK_N@Z; CVssIOCTLChannel::Unpack<uchar>(CVssFunctionTracer &,uchar *,ulong,bool)
0x18001a482  mov     rdi, [rbp+3C0h+var_2C8]
0x18001a489  test    edi, edi
0x18001a48b  js      short loc_18001A4D7
0x18001a48d  lea     rcx, [rsp+4C0h+var_450]; this
0x18001a492  call    ??1CVssIOCTLChannel@@QEAA@XZ; CVssIOCTLChannel::~CVssIOCTLChannel(void)
0x18001a497  nop
0x18001a498  lea     rcx, [rsp+4C0h+var_460]
0x18001a49d  call    ??1?$CVssAuto@PEAU_SID@@V?$CVssAllocatingPtr_Storage@PEAU_SID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZP6APEAX_K@Z$1?LocalAllocate@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&LocalFree(void *),void * (*)(unsigned __int64),&LocalAllocate(unsigned __int64)>>::~CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&LocalFree(void *),void * (*)(unsigned __int64),&LocalAllocate(unsigned __int64)>>(void)
0x18001a4a2  mov     dil, [rsp+4C0h+var_470]
0x18001a4a7  test    dword ptr [rbx+118h], 400000h
0x18001a4b1  jnz     short loc_18001A4B8
0x18001a4b3  test    dil, dil
0x18001a4b6  jz      short loc_18001A4C9
0x18001a4b8  mov     dl, 1; bool
0x18001a4ba  mov     rcx, rbx; this
0x18001a4bd  call    ?SetAutoRecoverAttribute@CVssQueuedSnapshot@@AEAAX_N@Z; CVssQueuedSnapshot::SetAutoRecoverAttribute(bool)
0x18001a4c2  mov     byte ptr [rbx+101h], 1
0x18001a4c9  lea     rcx, [rbp+3C0h+var_3A0]; this
0x18001a4cd  call    ??1CVssRegistryKey@@QEAA@XZ; CVssRegistryKey::~CVssRegistryKey(void)
0x18001a4d2  jmp     loc_18001A1F3
0x18001a4d7  mov     [rbp+3C0h+var_380], r12
0x18001a4db  mov     [rbp+3C0h+var_378], r13
0x18001a4df  lea     rax, aSprqsnpc; "SPRQSNPC"
0x18001a4e6  mov     [rbp+3C0h+var_370], rax
0x18001a4ea  mov     [rbp+3C0h+var_368], 175h
0x18001a4f1  mov     [rbp+3C0h+var_364], r15d
0x18001a4f5  mov     [rbp+3C0h+var_360], 0FFh
0x18001a4fc  mov     [rbp+3C0h+var_2E0], 1000000h
0x18001a506  xor     edx, edx; Val
0x18001a508  lea     r8d, [rdx+78h]; Size
0x18001a50c  lea     rcx, [rbp+3C0h+var_358]; void *
0x18001a510  call    memset_0
0x18001a515  mov     dword ptr [rsp+4C0h+lpMaximumComponentLength], edi
0x18001a519  lea     r9, aCvssioctlchann; "CVssIOCTLChannel::Unpack failed with hr"...
0x18001a520  mov     r8d, edi
0x18001a523  lea     rdx, [rbp+3C0h+var_380]
0x18001a527  lea     rcx, [rbp+3C0h+var_2D0]
0x18001a52e  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18001a534  mov     [rbp+3C0h+var_380], r12
0x18001a538  mov     [rbp+3C0h+var_378], r13
0x18001a53c  lea     rax, aSprqsnpc; "SPRQSNPC"
0x18001a543  mov     [rbp+3C0h+var_370], rax
0x18001a547  mov     [rbp+3C0h+var_368], 16Fh
0x18001a54e  mov     [rbp+3C0h+var_364], r15d
0x18001a552  mov     [rbp+3C0h+var_360], 0FFh
0x18001a559  mov     [rbp+3C0h+var_2E0], 1000000h
0x18001a563  xor     edx, edx; Val
0x18001a565  lea     r8d, [rdx+78h]; Size
0x18001a569  lea     rcx, [rbp+3C0h+var_358]; void *
0x18001a56d  call    memset_0
0x18001a572  mov     dword ptr [rsp+4C0h+lpMaximumComponentLength], edi
0x18001a576  lea     r9, aCvssioctlchann_9; "CVssIOCTLChannel::Call(FSCTL_TXFS_TRANS"...
0x18001a57d  mov     r8d, edi
0x18001a580  lea     rdx, [rbp+3C0h+var_380]
0x18001a584  lea     rcx, [rbp+3C0h+var_2D0]
0x18001a58b  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18001a591  mov     [rbp+3C0h+var_380], r12
0x18001a595  mov     [rbp+3C0h+var_378], r13
0x18001a599  lea     rax, aSprqsnpc; "SPRQSNPC"
0x18001a5a0  mov     [rbp+3C0h+var_370], rax
0x18001a5a4  mov     [rbp+3C0h+var_368], 169h
0x18001a5ab  mov     [rbp+3C0h+var_364], r15d
0x18001a5af  mov     [rbp+3C0h+var_360], 0FFh
0x18001a5b6  mov     [rbp+3C0h+var_2E0], 1000000h
0x18001a5c0  xor     edx, edx; Val
0x18001a5c2  lea     r8d, [rdx+78h]; Size
0x18001a5c6  lea     rcx, [rbp+3C0h+var_358]; void *
0x18001a5ca  call    memset_0
0x18001a5cf  mov     dword ptr [rsp+4C0h+lpMaximumComponentLength], edi
0x18001a5d3  lea     r9, aCvssioctlchann_7; "CVssIOCTLChannel::Open failed with hr: "...
0x18001a5da  mov     r8d, edi
0x18001a5dd  lea     rdx, [rbp+3C0h+var_380]
0x18001a5e1  lea     rcx, [rbp+3C0h+var_2D0]
0x18001a5e8  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
```
