# CVsSoftwareProvider::InternalDeleteSnapshots(_GUID,_VSS_OBJECT_TYPE,long,long *,_GUID *)

- ea: `0x180024a6c`
- end: `0x1800250b4`
- name: `?InternalDeleteSnapshots@CVsSoftwareProvider@@SAJU_GUID@@W4_VSS_OBJECT_TYPE@@JPEAJPEAU2@@Z`
- size: `1608`
- prototype: `__int64 __fastcall(struct _GUID *Buf2, enum _VSS_OBJECT_TYPE, int, int *, struct _GUID *)`
- caller_count: `3`
- callee_count: `23`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000de70`
- `0x1800186e0`
- `0x180023d70`

## callees

- `0x180001580`
- `0x18000212c`
- `0x180002f1c`
- `0x180003718`
- `0x1800039d8`
- `0x180003de8`
- `0x18000610c`
- `0x18000dbd0`
- `0x180015864`
- `0x180016ff0`
- `0x18001b65c`
- `0x18001c404`
- `0x18001d424`
- `0x18001d648`
- `0x180023834`
- `0x180024a6c`
- `0x180025228`
- `0x180033a8c`
- `0x180033c78`
- `0x18003649c`
- `0x1800367b8`
- `0x180037080`
- `0x1800419fc`

## string_xrefs

- `0x180024aae`: `base\stor\vss\modules\softprv\src\delete.cxx`
- `0x180024d29`: `base\stor\vss\modules\softprv\src\delete.cxx`
- `0x180024ddd`: `base\stor\vss\modules\softprv\src\delete.cxx`
- `0x180024f66`: `base\stor\vss\modules\softprv\src\delete.cxx`
- `0x180024fd6`: `base\stor\vss\modules\softprv\src\delete.cxx`
- `0x180024fb6`: `Incompatible type %d`
- `0x180024abc`: `CVsSoftwareProvider::InternalDeleteSnapshots`
- `0x180024d37`: `CVsSoftwareProvider::InternalDeleteSnapshots`
- `0x180024de8`: `CVsSoftwareProvider::InternalDeleteSnapshots`
- `0x180024f71`: `CVsSoftwareProvider::InternalDeleteSnapshots`
- `0x180024fe1`: `CVsSoftwareProvider::InternalDeleteSnapshots`
- `0x180024d8d`: `Warning: snapshot %s cannot be opened`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVsSoftwareProvider::InternalDeleteSnapshots(
        struct _GUID *Buf2,
        enum _VSS_OBJECT_TYPE a2,
        int a3,
        int *a4,
        struct _GUID *a5)
{
  int v9; // r9d
  char v10; // r15
  bool v11; // bl
  __int64 v12; // r9
  unsigned __int16 **Ref; // rax
  unsigned __int64 v14; // r8
  struct _VSS_SNAPSHOT_PROP *p_m_SnapshotSetId; // rcx
  unsigned int v16; // ebx
  unsigned __int16 *v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  bool v20; // [rsp+50h] [rbp-B0h] BYREF
  int v21; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v22[2]; // [rsp+60h] [rbp-A0h] BYREF
  void **v23; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v24; // [rsp+78h] [rbp-88h]
  __int64 v25; // [rsp+80h] [rbp-80h] BYREF
  char v26; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v27; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v28; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v29; // [rsp+A0h] [rbp-60h]
  int v30; // [rsp+A8h] [rbp-58h]
  int v31; // [rsp+ACh] [rbp-54h]
  int v32; // [rsp+B0h] [rbp-50h]
  _BYTE v33[120]; // [rsp+B8h] [rbp-48h] BYREF
  int v34; // [rsp+130h] [rbp+30h]
  LPVOID v35; // [rsp+140h] [rbp+40h] BYREF
  int v36; // [rsp+148h] [rbp+48h]
  __int64 v37; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v38; // [rsp+1B8h] [rbp+B8h]
  __int128 v39; // [rsp+1C8h] [rbp+C8h]
  __int16 v40; // [rsp+1D8h] [rbp+D8h]
  __int64 v41; // [rsp+1DCh] [rbp+DCh]
  __int64 v42; // [rsp+1E8h] [rbp+E8h]
  __int64 v43; // [rsp+1F0h] [rbp+F0h]
  int v44; // [rsp+1F8h] [rbp+F8h]
  __int64 v45; // [rsp+200h] [rbp+100h]
  __int16 v46; // [rsp+208h] [rbp+108h]
  void **v47; // [rsp+210h] [rbp+110h]
  __int64 v48; // [rsp+218h] [rbp+118h]
  __int64 v49; // [rsp+220h] [rbp+120h] BYREF
  __int128 v50; // [rsp+228h] [rbp+128h]
  __int128 v51; // [rsp+238h] [rbp+138h]
  __int16 v52; // [rsp+248h] [rbp+148h]
  __int64 v53; // [rsp+24Ch] [rbp+14Ch]
  __int64 v54; // [rsp+258h] [rbp+158h]
  __int64 v55; // [rsp+260h] [rbp+160h]
  int v56; // [rsp+268h] [rbp+168h]
  __int64 v57; // [rsp+270h] [rbp+170h]
  __int16 v58; // [rsp+278h] [rbp+178h]
  void **v59; // [rsp+280h] [rbp+180h]
  __int64 v60; // [rsp+288h] [rbp+188h]
  _QWORD v61[3]; // [rsp+290h] [rbp+190h] BYREF
  int v62; // [rsp+2A8h] [rbp+1A8h]
  int v63; // [rsp+2ACh] [rbp+1ACh]
  int v64; // [rsp+2B0h] [rbp+1B0h]
  _BYTE v65[120]; // [rsp+2B8h] [rbp+1B8h] BYREF
  int v66; // [rsp+330h] [rbp+230h]
  struct _VSS_SNAPSHOT_PROP Buf1; // [rsp+340h] [rbp+240h] BYREF
  int v68; // [rsp+3E0h] [rbp+2E0h]
  unsigned __int16 v69[264]; // [rsp+3F0h] [rbp+2F0h] BYREF
  unsigned __int16 v70[264]; // [rsp+600h] [rbp+500h] BYREF

  *(_QWORD *)&Buf1.m_SnapshotId.Data1 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
  *(_QWORD *)Buf1.m_SnapshotId.Data4 = L"CVsSoftwareProvider::InternalDeleteSnapshots";
  *(_QWORD *)&Buf1.m_SnapshotSetId.Data1 = L"SPRDELEC";
  *(_DWORD *)Buf1.m_SnapshotSetId.Data4 = 193;
  *(_DWORD *)&Buf1.m_SnapshotSetId.Data4[4] = 2;
  Buf1.m_lSnapshotsCount = 255;
  v68 = 0x1000000;
  memset_0(&Buf1.m_pwszSnapshotDeviceObject, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v35, (__int64)&Buf1, 0);
  v37 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v48 = 0;
  v47 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
  v38 = 0;
  v39 = 0;
  v49 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v60 = 0;
  v59 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
  v50 = 0;
  v51 = 0;
  v10 = 0;
  v11 = 0;
  v24 = 0;
  v23 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
  v25 = -1;
  v26 = 1;
  while ( !v11
       && CVssVolumeIterator::SelectNewVolume((CVssVolumeIterator *)&v25, (struct CVssFunctionTracer *)&v35, v70, v9) )
  {
    LOBYTE(v18) = 0;
    LOBYTE(v12) = 1;
    v36 = CVssIOCTLChannel::Open(&v37, &v35, v70, v12, (_DWORD)v18, 0, 0);
    if ( v36 < 0 || (v36 = CVssIOCTLChannel::Call(&v37, (__int64)&v35, 0x530018u, 0, 0, 0), v36 < 0) )
    {
      v36 = 0;
    }
    else
    {
      v21 = 0;
      CVssIOCTLChannel::Unpack<unsigned long>((CVssIOCTLChannel *)&v37, (struct CVssFunctionTracer *)&v35, &v21);
      while ( !v11 )
      {
        Ref = (unsigned __int16 **)CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::ResetAndGetRef(&v23);
        if ( !CVssIOCTLChannel::UnpackZeroString((CVssIOCTLChannel *)&v37, (struct CVssFunctionTracer *)&v35, Ref) )
          break;
        VssConcatenate((struct CVssFunctionTracer *)&v35, v69, v14, L"\\\\?\\GLOBALROOT", v24);
        LOBYTE(v19) = 0;
        v36 = CVssIOCTLChannel::Open(&v49, &v35, v69, 0, v19, 0, 0);
        if ( v36 >= 0 )
        {
          v36 = CVssIOCTLChannel::Call(&v49, (__int64)&v35, 0x53019Cu, 0, 0, 0);
          if ( v36 >= 0 )
          {
            Buf1.m_SnapshotId.Data1 = 0;
            memset_0(&Buf1.m_SnapshotId.Data2, 0, 0x7Cu);
            v21 = 0;
            v20 = 0;
            v22[0] = &CVssAuto<_VSS_SNAPSHOT_PROP *,CVssAutoGenericValue_Storage<_VSS_SNAPSHOT_PROP *,0,void (*)(_VSS_SNAPSHOT_PROP *),&void VssFreeSnapshotProperties(_VSS_SNAPSHOT_PROP *),_VSS_SNAPSHOT_PROP * & (*)(_VSS_SNAPSHOT_PROP * &),&public: static _VSS_SNAPSHOT_PROP * & DTyper<_VSS_SNAPSHOT_PROP *>::Identity(_VSS_SNAPSHOT_PROP * &)>>::`vftable';
            v22[1] = &Buf1;
            if ( CVssQueuedSnapshot::LoadStructure((struct CVssIOCTLChannel *)&v49, &Buf1, &v21, &v20, 0) )
            {
              if ( a2 == VSS_OBJECT_SNAPSHOT_SET )
              {
                p_m_SnapshotSetId = (struct _VSS_SNAPSHOT_PROP *)&Buf1.m_SnapshotSetId;
              }
              else
              {
                if ( a2 != VSS_OBJECT_SNAPSHOT )
                {
                  v27 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
                  v28 = L"CVsSoftwareProvider::InternalDeleteSnapshots";
                  v29 = L"SPRDELEC";
                  v30 = 307;
                  v31 = 2;
                  v32 = 255;
                  v34 = 0x1000000;
                  memset_0(v33, 0, sizeof(v33));
                  LODWORD(v18) = a2;
                  CVssFunctionTracer::TranslateGenericError(&v35, &v27, 2147549183LL, L"Incompatible type %d", v18);
                }
                p_m_SnapshotSetId = &Buf1;
              }
              if ( !memcmp_0(p_m_SnapshotSetId, Buf2, 0x10u) )
              {
                v11 = a2 == VSS_OBJECT_SNAPSHOT;
                if ( (a3 == -1 || ((a3 ^ v21) & 0xFF3FFFFF) == 0) && !v20 )
                {
                  v10 = 1;
                  *a5 = Buf1.m_SnapshotId;
                  CVsSoftwareProvider::DeleteSnapshot(v70, v24, v69, &Buf1, (int)v18);
                  ++*a4;
                }
              }
            }
            CVssAuto<_VSS_SNAPSHOT_PROP *,CVssAutoGenericValue_Storage<_VSS_SNAPSHOT_PROP *,0,void (*)(_VSS_SNAPSHOT_PROP *),&void VssFreeSnapshotProperties(_VSS_SNAPSHOT_PROP *),_VSS_SNAPSHOT_PROP * & (*)(_VSS_SNAPSHOT_PROP * &),&public: static _VSS_SNAPSHOT_PROP * & DTyper<_VSS_SNAPSHOT_PROP *>::Identity(_VSS_SNAPSHOT_PROP * &)>>::~CVssAuto<_VSS_SNAPSHOT_PROP *,CVssAutoGenericValue_Storage<_VSS_SNAPSHOT_PROP *,0,void (*)(_VSS_SNAPSHOT_PROP *),&void VssFreeSnapshotProperties(_VSS_SNAPSHOT_PROP *),_VSS_SNAPSHOT_PROP * & (*)(_VSS_SNAPSHOT_PROP * &),&public: static _VSS_SNAPSHOT_PROP * & DTyper<_VSS_SNAPSHOT_PROP *>::Identity(_VSS_SNAPSHOT_PROP * &)>>(v22);
          }
          else
          {
            v27 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
            v28 = L"CVsSoftwareProvider::InternalDeleteSnapshots";
            v29 = L"SPRDELEC";
            v30 = 269;
            v31 = 2;
            v32 = 255;
            v34 = 0x1000000;
            memset_0(v33, 0, sizeof(v33));
            CVssFunctionTracer::Trace(&v35, &v27, L"Warning: snapshot %s cannot be queried for properties", v69);
          }
        }
        else
        {
          v61[0] = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
          v61[1] = L"CVsSoftwareProvider::InternalDeleteSnapshots";
          v61[2] = L"SPRDELEC";
          v62 = 261;
          v63 = 2;
          v64 = 255;
          v66 = 0x1000000;
          memset_0(v65, 0, sizeof(v65));
          CVssFunctionTracer::Trace(&v35, v61, L"Warning: snapshot %s cannot be opened", v69);
        }
      }
      CVsSoftwareProvider::PurgeSnapshotsOnVolume(v70, 0xFFFFFFFF, 0);
    }
  }
  if ( !v10 )
  {
    v27 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
    v28 = L"CVsSoftwareProvider::InternalDeleteSnapshots";
    v29 = L"SPRDELEC";
    v30 = 348;
    v31 = 2;
    v32 = 255;
    v34 = 0x1000000;
    memset_0(v33, 0, sizeof(v33));
    CVssFunctionTracer::Throw(&v35, &v27, 2147754760LL, L"Object not found");
  }
  if ( v36 >= 0 )
    *a5 = GUID_NULL;
  v16 = v36;
  CVssVolumeIterator::~CVssVolumeIterator((HANDLE *)&v25);
  CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v23);
  CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v49);
  CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v37);
  CVssFunctionTracer::~CVssFunctionTracer(&v35);
  return v16;
}

```

## disassembly

```asm
0x180024a6c  mov     [rsp-8+arg_0], rbx
0x180024a71  push    rbp
0x180024a72  push    rsi
0x180024a73  push    rdi
0x180024a74  push    r12
0x180024a76  push    r13
0x180024a78  push    r14
0x180024a7a  push    r15
0x180024a7c  lea     rbp, [rsp-720h]
0x180024a84  sub     rsp, 820h
0x180024a8b  mov     rax, cs:__security_cookie
0x180024a92  xor     rax, rsp
0x180024a95  mov     [rbp+750h+var_40], rax
0x180024a9c  mov     r13, r9
0x180024a9f  mov     r14d, r8d
0x180024aa2  mov     edi, edx
0x180024aa4  mov     r12, rcx
0x180024aa7  mov     rsi, [rbp+750h+arg_20]
0x180024aae  lea     rax, aBaseStorVssMod_5; "base\\stor\\vss\\modules\\softprv\\src"...
0x180024ab5  mov     [rbp+750h+Buf1], rax
0x180024abc  lea     rax, aCvssoftwarepro_12; "CVsSoftwareProvider::InternalDeleteSnap"...
0x180024ac3  mov     [rbp+750h+var_508], rax
0x180024aca  lea     rax, aSprdelec; "SPRDELEC"
0x180024ad1  mov     [rbp+750h+var_500], rax
0x180024ad8  mov     [rbp+750h+var_4F8], 0C1h
0x180024ae2  mov     [rbp+750h+var_4F4], 2
0x180024aec  mov     [rbp+750h+var_4F0], 0FFh
0x180024af6  mov     [rbp+750h+var_470], 1000000h
0x180024b00  xor     edx, edx; Val
0x180024b02  lea     r8d, [rdx+78h]; Size
0x180024b06  lea     rcx, [rbp+750h+var_4E8]; void *
0x180024b0d  call    memset_0
0x180024b12  xor     r8d, r8d
0x180024b15  lea     rdx, [rbp+750h+Buf1]
0x180024b1c  lea     rcx, [rbp+750h+var_710]
0x180024b20  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180024b25  nop
0x180024b26  xor     edx, edx
0x180024b28  mov     [rbp+750h+var_6A0], rdx
0x180024b2f  mov     [rbp+750h+var_678], dx
0x180024b36  mov     [rbp+750h+var_674], rdx
0x180024b3d  mov     [rbp+750h+var_668], rdx
0x180024b44  mov     [rbp+750h+var_660], rdx
0x180024b4b  mov     [rbp+750h+var_658], edx
0x180024b51  mov     [rbp+750h+var_650], rdx
0x180024b58  mov     [rbp+750h+var_648], dx
0x180024b5f  mov     [rbp+750h+var_638], rdx
0x180024b66  lea     rcx, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x180024b6d  mov     [rbp+750h+var_640], rcx
0x180024b74  xorps   xmm0, xmm0
0x180024b77  movups  [rbp+750h+var_698], xmm0
0x180024b7e  movups  [rbp+750h+var_688], xmm0
0x180024b85  mov     [rbp+750h+var_630], rdx
0x180024b8c  mov     [rbp+750h+var_608], dx
0x180024b93  mov     [rbp+750h+var_604], rdx
0x180024b9a  mov     [rbp+750h+var_5F8], rdx
0x180024ba1  mov     [rbp+750h+var_5F0], rdx
0x180024ba8  mov     [rbp+750h+var_5E8], edx
0x180024bae  mov     [rbp+750h+var_5E0], rdx
0x180024bb5  mov     [rbp+750h+var_5D8], dx
0x180024bbc  mov     [rbp+750h+var_5C8], rdx
0x180024bc3  mov     [rbp+750h+var_5D0], rcx
0x180024bca  movups  [rbp+750h+var_628], xmm0
0x180024bd1  movups  [rbp+750h+var_618], xmm0
0x180024bd8  mov     r15b, dl
0x180024bdb  mov     bl, dl
0x180024bdd  mov     [rsp+850h+var_7D8], rdx
0x180024be2  mov     [rsp+850h+var_7E0], rcx
0x180024be7  mov     [rbp+750h+var_7D0], 0FFFFFFFFFFFFFFFFh
0x180024bef  mov     [rbp+750h+var_7C8], 1
0x180024bf3  test    bl, bl
0x180024bf5  jnz     loc_180024FD1
0x180024bfb  lea     r8, [rbp+750h+var_250]; unsigned __int16 *
0x180024c02  lea     rdx, [rbp+750h+var_710]; struct CVssFunctionTracer *
0x180024c06  lea     rcx, [rbp+750h+var_7D0]; this
0x180024c0a  call    ?SelectNewVolume@CVssVolumeIterator@@QEAA_NAEAVCVssFunctionTracer@@PEAGH@Z; CVssVolumeIterator::SelectNewVolume(CVssFunctionTracer &,ushort *,int)
0x180024c0f  xor     edx, edx
0x180024c11  test    al, al
0x180024c13  jz      loc_180024FD1
0x180024c19  mov     [rsp+850h+var_810], 80h
0x180024c21  mov     dword ptr [rsp+850h+var_820], edx
0x180024c25  mov     [rsp+850h+var_828], edx
0x180024c29  mov     byte ptr [rsp+850h+var_830], dl
0x180024c2d  mov     r9b, 1
0x180024c30  lea     r8, [rbp+750h+var_250]
0x180024c37  lea     rdx, [rbp+750h+var_710]
0x180024c3b  lea     rcx, [rbp+750h+var_6A0]
0x180024c42  call    ?Open@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@PEBG_N2W4_VSS_ICHANNEL_LOGGING@@KKK@Z; CVssIOCTLChannel::Open(CVssFunctionTracer &,ushort const *,bool,bool,_VSS_ICHANNEL_LOGGING,ulong,ulong,ulong)
0x180024c47  mov     [rbp+750h+var_708], eax
0x180024c4a  xor     edx, edx
0x180024c4c  test    eax, eax
0x180024c4e  jns     short loc_180024C55
0x180024c50  mov     [rbp+750h+var_708], edx
0x180024c53  jmp     short loc_180024BF3
0x180024c55  mov     [rsp+850h+var_820], rdx
0x180024c5a  mov     byte ptr [rsp+850h+var_828], dl
0x180024c5e  mov     dword ptr [rsp+850h+var_830], edx
0x180024c62  xor     r9d, r9d
0x180024c65  mov     r8d, 530018h
0x180024c6b  lea     rdx, [rbp+750h+var_710]
0x180024c6f  lea     rcx, [rbp+750h+var_6A0]
0x180024c76  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x180024c7b  mov     [rbp+750h+var_708], eax
0x180024c7e  xor     edx, edx
0x180024c80  test    eax, eax
0x180024c82  js      short loc_180024C50
0x180024c84  mov     [rsp+850h+var_7F8], edx
0x180024c88  lea     r8, [rsp+850h+var_7F8]
0x180024c8d  lea     rdx, [rbp+750h+var_710]
0x180024c91  lea     rcx, [rbp+750h+var_6A0]
0x180024c98  call    ??$Unpack@K@CVssIOCTLChannel@@QEAAXAEAVCVssFunctionTracer@@PEAKK_N@Z; CVssIOCTLChannel::Unpack<ulong>(CVssFunctionTracer &,ulong *,ulong,bool)
0x180024c9d  test    bl, bl
0x180024c9f  jnz     loc_180024F4D
0x180024ca5  lea     rcx, [rsp+850h+var_7E0]
0x180024caa  call    ?ResetAndGetRef@?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@QEAAAEAPEAGXZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::ResetAndGetRef(void)
0x180024caf  mov     r8, rax; unsigned __int16 **
0x180024cb2  lea     rdx, [rbp+750h+var_710]; struct CVssFunctionTracer *
0x180024cb6  lea     rcx, [rbp+750h+var_6A0]; this
0x180024cbd  call    ?UnpackZeroString@CVssIOCTLChannel@@QEAAPEBGAEAVCVssFunctionTracer@@AEAPEAG@Z; CVssIOCTLChannel::UnpackZeroString(CVssFunctionTracer &,ushort * &)
0x180024cc2  test    rax, rax
0x180024cc5  jz      loc_180024F4D
0x180024ccb  mov     rax, [rsp+850h+var_7D8]
0x180024cd0  mov     [rsp+850h+var_830], rax; unsigned __int16 *
0x180024cd5  lea     r9, aGlobalroot_3; "\\\\?\\GLOBALROOT"
0x180024cdc  lea     rdx, [rbp+750h+var_460]; unsigned __int16 *
0x180024ce3  lea     rcx, [rbp+750h+var_710]; struct CVssFunctionTracer *
0x180024ce7  call    ?VssConcatenate@@YAXAEAVCVssFunctionTracer@@PEAG_KPEBG3@Z; VssConcatenate(CVssFunctionTracer &,ushort *,unsigned __int64,ushort const *,ushort const *)
0x180024cec  mov     [rsp+850h+var_810], 80h
0x180024cf4  xor     eax, eax
0x180024cf6  mov     dword ptr [rsp+850h+var_820], eax
0x180024cfa  mov     [rsp+850h+var_828], eax
0x180024cfe  mov     byte ptr [rsp+850h+var_830], al
0x180024d02  xor     r9d, r9d
0x180024d05  lea     r8, [rbp+750h+var_460]
0x180024d0c  lea     rdx, [rbp+750h+var_710]
0x180024d10  lea     rcx, [rbp+750h+var_630]
0x180024d17  call    ?Open@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@PEBG_N2W4_VSS_ICHANNEL_LOGGING@@KKK@Z; CVssIOCTLChannel::Open(CVssFunctionTracer &,ushort const *,bool,bool,_VSS_ICHANNEL_LOGGING,ulong,ulong,ulong)
0x180024d1c  mov     [rbp+750h+var_708], eax
0x180024d1f  xor     ecx, ecx
0x180024d21  test    eax, eax
0x180024d23  jns     loc_180024DB0
0x180024d29  lea     rax, aBaseStorVssMod_5; "base\\stor\\vss\\modules\\softprv\\src"...
0x180024d30  mov     [rbp+750h+var_5C0], rax
0x180024d37  lea     rax, aCvssoftwarepro_12; "CVsSoftwareProvider::InternalDeleteSnap"...
0x180024d3e  mov     [rbp+750h+var_5B8], rax
0x180024d45  lea     rax, aSprdelec; "SPRDELEC"
0x180024d4c  mov     [rbp+750h+var_5B0], rax
0x180024d53  mov     [rbp+750h+var_5A8], 105h
0x180024d5d  mov     [rbp+750h+var_5A4], 2
0x180024d67  mov     [rbp+750h+var_5A0], 0FFh
0x180024d71  mov     [rbp+750h+var_520], 1000000h
0x180024d7b  xor     edx, edx; Val
0x180024d7d  lea     r8d, [rcx+78h]; Size
0x180024d81  lea     rcx, [rbp+750h+var_598]; void *
0x180024d88  call    memset_0
0x180024d8d  lea     r8, aWarningSnapsho_0; "Warning: snapshot %s cannot be opened"
0x180024d94  lea     rdx, [rbp+750h+var_5C0]
0x180024d9b  lea     r9, [rbp+750h+var_460]
0x180024da2  lea     rcx, [rbp+750h+var_710]
0x180024da6  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180024dab  jmp     loc_180024C9D
0x180024db0  mov     [rsp+850h+var_820], rcx
0x180024db5  mov     byte ptr [rsp+850h+var_828], cl
0x180024db9  mov     dword ptr [rsp+850h+var_830], ecx
0x180024dbd  xor     r9d, r9d
0x180024dc0  mov     r8d, 53019Ch
0x180024dc6  lea     rdx, [rbp+750h+var_710]
0x180024dca  lea     rcx, [rbp+750h+var_630]
0x180024dd1  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x180024dd6  mov     [rbp+750h+var_708], eax
0x180024dd9  test    eax, eax
0x180024ddb  jns     short loc_180024E39
0x180024ddd  lea     rax, aBaseStorVssMod_5; "base\\stor\\vss\\modules\\softprv\\src"...
0x180024de4  mov     [rbp+750h+var_7C0], rax
0x180024de8  lea     rax, aCvssoftwarepro_12; "CVsSoftwareProvider::InternalDeleteSnap"...
0x180024def  mov     [rbp+750h+var_7B8], rax
0x180024df3  lea     rax, aSprdelec; "SPRDELEC"
0x180024dfa  mov     [rbp+750h+var_7B0], rax
0x180024dfe  mov     [rbp+750h+var_7A8], 10Dh
0x180024e05  mov     [rbp+750h+var_7A4], 2
0x180024e0c  mov     [rbp+750h+var_7A0], 0FFh
0x180024e13  mov     [rbp+750h+var_720], 1000000h
0x180024e1a  xor     edx, edx; Val
0x180024e1c  lea     r8d, [rdx+78h]; Size
0x180024e20  lea     rcx, [rbp+750h+var_798]; void *
0x180024e24  call    memset_0
0x180024e29  lea     r8, aWarningSnapsho; "Warning: snapshot %s cannot be queried "...
0x180024e30  lea     rdx, [rbp+750h+var_7C0]
0x180024e34  jmp     loc_180024D9B
0x180024e39  mov     dword ptr [rbp+750h+Buf1], 0
0x180024e43  xor     edx, edx; Val
0x180024e45  lea     r8d, [rdx+7Ch]; Size
0x180024e49  lea     rcx, [rbp+750h+Buf1+4]; void *
0x180024e50  call    memset_0
0x180024e55  xor     ecx, ecx
0x180024e57  mov     [rsp+850h+var_7F8], ecx
0x180024e5b  mov     [rsp+850h+var_800], cl
0x180024e5f  lea     rax, ??_7?$CVssAuto@PEAU_VSS_SNAPSHOT_PROP@@V?$CVssAutoGenericValue_Storage@PEAU_VSS_SNAPSHOT_PROP@@$0A@P6AXPEAU1@@Z$1?VssFreeSnapshotProperties@@YAX0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAU_VSS_SNAPSHOT_PROP@@@@SAAEAPEAU1@1@Z@@@@6B@; const CVssAuto<_VSS_SNAPSHOT_PROP *,CVssAutoGenericValue_Storage<_VSS_SNAPSHOT_PROP *,0,void (*)(_VSS_SNAPSHOT_PROP *),&VssFreeSnapshotProperties(_VSS_SNAPSHOT_PROP *),_VSS_SNAPSHOT_PROP * & (*)(_VSS_SNAPSHOT_PROP * &),&DTyper<_VSS_SNAPSHOT_PROP *>::Identity(_VSS_SNAPSHOT_PROP * &)>>::`vftable'
0x180024e66  mov     [rsp+850h+var_7F0], rax
0x180024e6b  lea     rax, [rbp+750h+Buf1]
0x180024e72  mov     [rsp+850h+var_7E8], rax
0x180024e77  mov     byte ptr [rsp+850h+var_830], cl; int
0x180024e7b  lea     r9, [rsp+850h+var_800]; bool *
0x180024e80  lea     r8, [rsp+850h+var_7F8]; int *
0x180024e85  lea     rdx, [rbp+750h+Buf1]; struct _VSS_SNAPSHOT_PROP *
0x180024e8c  lea     rcx, [rbp+750h+var_630]; struct CVssIOCTLChannel *
0x180024e93  call    ?LoadStructure@CVssQueuedSnapshot@@SA_NAEAVCVssIOCTLChannel@@PEAU_VSS_SNAPSHOT_PROP@@PEAJPEA_N_N@Z; CVssQueuedSnapshot::LoadStructure(CVssIOCTLChannel &,_VSS_SNAPSHOT_PROP *,long *,bool *,bool)
0x180024e98  test    al, al
0x180024e9a  jz      loc_180024F32
0x180024ea0  mov     ecx, edi
0x180024ea2  sub     ecx, 2
0x180024ea5  jz      loc_180024F41
0x180024eab  cmp     ecx, 1
0x180024eae  jnz     loc_180024F66
0x180024eb4  lea     rcx, [rbp+750h+Buf1]; Buf1
0x180024ebb  mov     r8d, 10h; Size
0x180024ec1  mov     rdx, r12; Buf2
0x180024ec4  call    memcmp_0
0x180024ec9  test    eax, eax
0x180024ecb  jnz     short loc_180024F32
0x180024ecd  cmp     edi, 3
0x180024ed0  setz    bl
0x180024ed3  cmp     r14d, 0FFFFFFFFh
0x180024ed7  jz      short loc_180024EE7
0x180024ed9  mov     eax, [rsp+850h+var_7F8]
0x180024edd  xor     eax, r14d
0x180024ee0  test    eax, 0FF3FFFFFh
0x180024ee5  jnz     short loc_180024F32
0x180024ee7  cmp     [rsp+850h+var_800], 0
0x180024eec  jnz     short loc_180024F32
0x180024eee  mov     r15b, 1
0x180024ef1  mov     eax, dword ptr [rbp+750h+Buf1]
0x180024ef7  mov     [rsi], eax
0x180024ef9  movsd   xmm0, [rbp+750h+Buf1+4]
0x180024f01  movsd   qword ptr [rsi+4], xmm0
0x180024f06  mov     eax, dword ptr [rbp+750h+var_508+4]
0x180024f0c  mov     [rsi+0Ch], eax
0x180024f0f  lea     r9, [rbp+750h+Buf1]; struct _VSS_SNAPSHOT_PROP *
0x180024f16  lea     r8, [rbp+750h+var_460]; unsigned __int16 *
0x180024f1d  mov     rdx, [rsp+850h+var_7D8]; unsigned __int16 *
0x180024f22  lea     rcx, [rbp+750h+var_250]; unsigned __int16 *
0x180024f29  call    ?DeleteSnapshot@CVsSoftwareProvider@@CA_NPEAG00AEAU_VSS_SNAPSHOT_PROP@@J@Z; CVsSoftwareProvider::DeleteSnapshot(ushort *,ushort *,ushort *,_VSS_SNAPSHOT_PROP &,long)
0x180024f2e  inc     dword ptr [r13+0]
0x180024f32  lea     rcx, [rsp+850h+var_7F0]
0x180024f37  call    ??1?$CVssAuto@PEAU_VSS_SNAPSHOT_PROP@@V?$CVssAutoGenericValue_Storage@PEAU_VSS_SNAPSHOT_PROP@@$0A@P6AXPEAU1@@Z$1?VssFreeSnapshotProperties@@YAX0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAU_VSS_SNAPSHOT_PROP@@@@SAAEAPEAU1@1@Z@@@@UEAA@XZ; CVssAuto<_VSS_SNAPSHOT_PROP *,CVssAutoGenericValue_Storage<_VSS_SNAPSHOT_PROP *,0,void (*)(_VSS_SNAPSHOT_PROP *),&VssFreeSnapshotProperties(_VSS_SNAPSHOT_PROP *),_VSS_SNAPSHOT_PROP * & (*)(_VSS_SNAPSHOT_PROP * &),&DTyper<_VSS_SNAPSHOT_PROP *>::Identity(_VSS_SNAPSHOT_PROP * &)>>::~CVssAuto<_VSS_SNAPSHOT_PROP *,CVssAutoGenericValue_Storage<_VSS_SNAPSHOT_PROP *,0,void (*)(_VSS_SNAPSHOT_PROP *),&VssFreeSnapshotProperties(_VSS_SNAPSHOT_PROP *),_VSS_SNAPSHOT_PROP * & (*)(_VSS_SNAPSHOT_PROP * &),&DTyper<_VSS_SNAPSHOT_PROP *>::Identity(_VSS_SNAPSHOT_PROP * &)>>(void)
0x180024f3c  jmp     loc_180024C9D
0x180024f41  lea     rcx, [rbp+750h+var_500]
0x180024f48  jmp     loc_180024EBB
0x180024f4d  xor     r8d, r8d; bool
0x180024f50  or      edx, 0FFFFFFFFh; unsigned int
0x180024f53  lea     rcx, [rbp+750h+var_250]; unsigned __int16 *
0x180024f5a  call    ?PurgeSnapshotsOnVolume@CVsSoftwareProvider@@CAXPEAGK_N@Z; CVsSoftwareProvider::PurgeSnapshotsOnVolume(ushort *,ulong,bool)
0x180024f5f  xor     edx, edx
0x180024f61  jmp     loc_180024BF3
0x180024f66  lea     rax, aBaseStorVssMod_5; "base\\stor\\vss\\modules\\softprv\\src"...
0x180024f6d  mov     [rbp+750h+var_7C0], rax
0x180024f71  lea     rax, aCvssoftwarepro_12; "CVsSoftwareProvider::InternalDeleteSnap"...
0x180024f78  mov     [rbp+750h+var_7B8], rax
0x180024f7c  lea     rax, aSprdelec; "SPRDELEC"
0x180024f83  mov     [rbp+750h+var_7B0], rax
0x180024f87  mov     [rbp+750h+var_7A8], 133h
0x180024f8e  mov     [rbp+750h+var_7A4], 2
0x180024f95  mov     [rbp+750h+var_7A0], 0FFh
0x180024f9c  mov     [rbp+750h+var_720], 1000000h
0x180024fa3  xor     edx, edx; Val
0x180024fa5  lea     r8d, [rdx+78h]; Size
0x180024fa9  lea     rcx, [rbp+750h+var_798]; void *
0x180024fad  call    memset_0
0x180024fb2  mov     dword ptr [rsp+850h+var_830], edi
0x180024fb6  lea     r9, aIncompatibleTy; "Incompatible type %d"
0x180024fbd  mov     r8d, 8000FFFFh
0x180024fc3  lea     rdx, [rbp+750h+var_7C0]
0x180024fc7  lea     rcx, [rbp+750h+var_710]
0x180024fcb  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x180024fd1  test    r15b, r15b
0x180024fd4  jnz     short loc_18002503D
0x180024fd6  lea     rax, aBaseStorVssMod_5; "base\\stor\\vss\\modules\\softprv\\src"...
0x180024fdd  mov     [rbp+750h+var_7C0], rax
0x180024fe1  lea     rax, aCvssoftwarepro_12; "CVsSoftwareProvider::InternalDeleteSnap"...
0x180024fe8  mov     [rbp+750h+var_7B8], rax
0x180024fec  lea     rax, aSprdelec; "SPRDELEC"
0x180024ff3  mov     [rbp+750h+var_7B0], rax
0x180024ff7  mov     [rbp+750h+var_7A8], 15Ch
0x180024ffe  mov     [rbp+750h+var_7A4], 2
0x180025005  mov     [rbp+750h+var_7A0], 0FFh
0x18002500c  mov     [rbp+750h+var_720], 1000000h
0x180025013  xor     edx, edx; Val
0x180025015  lea     r8d, [rdx+78h]; Size
0x180025019  lea     rcx, [rbp+750h+var_798]; void *
0x18002501d  call    memset_0
0x180025022  lea     r9, aObjectNotFound; "Object not found"
0x180025029  mov     r8d, 80042308h
0x18002502f  lea     rdx, [rbp+750h+var_7C0]
0x180025033  lea     rcx, [rbp+750h+var_710]
0x180025037  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18002503d  cmp     [rbp+750h+var_708], edx
0x180025040  jl      short loc_18002504D
0x180025042  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180025049  movdqu  xmmword ptr [rsi], xmm0
0x18002504d  mov     ebx, [rbp+750h+var_708]
  ... truncated ...
```
