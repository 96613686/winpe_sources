# CVsSoftwareProvider::HideSnapshotForDelete(CVssIOCTLChannel &)

- ea: `0x180024710`
- end: `0x180024a63`
- name: `?HideSnapshotForDelete@CVsSoftwareProvider@@CAXAEAVCVssIOCTLChannel@@@Z`
- size: `851`
- prototype: `void __fastcall(struct CVssIOCTLChannel *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180023834`

## callees

- `0x18000212c`
- `0x18000313c`
- `0x180003de8`
- `0x180018334`
- `0x180024710`
- `0x180033a8c`
- `0x180033c78`
- `0x18003649c`
- `0x1800367b8`

## string_xrefs

- `0x18002472c`: `base\stor\vss\modules\softprv\src\delete.cxx`
- `0x180024738`: `CVsSoftwareProvider::HideSnapshotForDelete`
- `0x18002483b`: `Snapshot volume is already hidden`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CVsSoftwareProvider::HideSnapshotForDelete(struct CVssIOCTLChannel *this)
{
  int v2; // edi
  __int64 v3; // rdi
  int v4; // edi
  __int64 v5; // rbx
  const unsigned __int16 *v6; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v7; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v8; // [rsp+50h] [rbp-B0h]
  int v9; // [rsp+58h] [rbp-A8h]
  int v10; // [rsp+5Ch] [rbp-A4h]
  int v11; // [rsp+60h] [rbp-A0h]
  _BYTE v12[120]; // [rsp+68h] [rbp-98h] BYREF
  int v13; // [rsp+E0h] [rbp-20h]
  __int64 v14; // [rsp+E8h] [rbp-18h]
  __int64 v15; // [rsp+F0h] [rbp-10h]
  LPVOID v16; // [rsp+100h] [rbp+0h] BYREF
  int v17; // [rsp+108h] [rbp+8h]
  __int64 v18; // [rsp+1C0h] [rbp+C0h] BYREF

  v6 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
  v7 = L"CVsSoftwareProvider::HideSnapshotForDelete";
  v8 = L"SPRDELEC";
  v9 = 800;
  v10 = 2;
  v11 = 255;
  v13 = 0x1000000;
  memset_0(v12, 0, sizeof(v12));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v16, (__int64)&v6, 0);
  v18 = 0;
  v15 = 0;
  *((_DWORD *)this + 11) = 0;
  *((_DWORD *)this + 16) = 0;
  v2 = CVssIOCTLChannel::Call(this, (__int64)&v16, 0x560038u, 0, 0, 0);
  v17 = v2;
  if ( v2 < 0 )
  {
    v6 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
    v7 = L"CVsSoftwareProvider::HideSnapshotForDelete";
    v8 = L"SPRDELEC";
    v9 = 816;
    v10 = 2;
    v11 = 255;
    v13 = 0x1000000;
    memset_0(v12, 0, sizeof(v12));
    CVssFunctionTracer::Throw(&v16, &v6, (unsigned int)v2, L"Cannot find GPT attributes for %s", *((_QWORD *)this + 13));
  }
  CVssIOCTLChannel::Unpack<__int64>(this, (struct CVssFunctionTracer *)&v16, &v18);
  if ( (v18 & 0x4000000000000000LL) != 0 )
  {
    v6 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
    v7 = L"CVsSoftwareProvider::HideSnapshotForDelete";
    v8 = L"SPRDELEC";
    v9 = 822;
    v10 = 2;
    v11 = 255;
    v13 = 0x1000000;
    memset_0(v12, 0, sizeof(v12));
    CVssFunctionTracer::Trace(&v16, &v6, L"Snapshot volume is already hidden");
  }
  else
  {
    v14 = v18 | 0x4000000000000000LL;
    *((_DWORD *)this + 11) = 0;
    *((_DWORD *)this + 16) = 0;
    CVssIOCTLChannel::PackArray<_VOLUME_SET_GPT_ATTRIBUTES_INFORMATION>(this, (struct CVssFunctionTracer *)&v16);
    v17 = CVssIOCTLChannel::Call(this, (__int64)&v16, 0x560034u, 0, 0, 0);
    v3 = *((_QWORD *)this + 13);
    v6 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
    v7 = L"CVsSoftwareProvider::HideSnapshotForDelete";
    v8 = L"SPRDELEC";
    v10 = 2;
    v11 = 255;
    v13 = 0x1000000;
    if ( v17 < 0 )
    {
      v9 = 842;
      memset_0(v12, 0, sizeof(v12));
      CVssFunctionTracer::Trace(&v16, &v6, L"Fail to set GPT attributes for %s. Retry with all connected volumes", v3);
      BYTE1(v15) = 1;
      *((_DWORD *)this + 11) = 0;
      *((_DWORD *)this + 16) = 0;
      CVssIOCTLChannel::PackArray<_VOLUME_SET_GPT_ATTRIBUTES_INFORMATION>(this, (struct CVssFunctionTracer *)&v16);
      v4 = CVssIOCTLChannel::Call(this, (__int64)&v16, 0x560034u, 0, 0, 0);
      v17 = v4;
      v5 = *((_QWORD *)this + 13);
      v6 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
      v7 = L"CVsSoftwareProvider::HideSnapshotForDelete";
      v8 = L"SPRDELEC";
      v10 = 2;
      v11 = 255;
      v13 = 0x1000000;
      if ( v4 < 0 )
      {
        v9 = 857;
        memset_0(v12, 0, sizeof(v12));
        CVssFunctionTracer::Throw(&v16, &v6, (unsigned int)v4, L"Failed to hide snapshot %s", v5);
      }
      v9 = 853;
      memset_0(v12, 0, sizeof(v12));
      CVssFunctionTracer::Trace(&v16, &v6, L"Hidden connected snapshot volume %s. ", v5);
    }
    else
    {
      v9 = 837;
      memset_0(v12, 0, sizeof(v12));
      CVssFunctionTracer::Trace(&v16, &v6, L"Hidden snapshot volume %s. ", v3);
    }
  }
  CVssFunctionTracer::~CVssFunctionTracer(&v16);
}

```

## disassembly

```asm
0x180024710  push    rbp
0x180024712  push    rbx
0x180024713  push    rsi
0x180024714  push    rdi
0x180024715  push    r12
0x180024717  push    r13
0x180024719  push    r14
0x18002471b  push    r15
0x18002471d  lea     rbp, [rsp-78h]
0x180024722  sub     rsp, 178h
0x180024729  mov     rbx, rcx
0x18002472c  lea     r14, aBaseStorVssMod_5; "base\\stor\\vss\\modules\\softprv\\src"...
0x180024733  mov     [rsp+1B0h+var_170], r14
0x180024738  lea     r15, aCvssoftwarepro_3; "CVsSoftwareProvider::HideSnapshotForDel"...
0x18002473f  mov     [rsp+1B0h+var_168], r15
0x180024744  lea     r12, aSprdelec; "SPRDELEC"
0x18002474b  mov     [rsp+1B0h+var_160], r12
0x180024750  mov     [rsp+1B0h+var_158], 320h
0x180024758  mov     r13d, 2
0x18002475e  mov     [rsp+1B0h+var_154], r13d
0x180024763  mov     [rsp+1B0h+var_150], 0FFh
0x18002476b  xor     esi, esi
0x18002476d  mov     [rbp+0B0h+var_D0], 1000000h
0x180024774  xor     edx, edx; Val
0x180024776  lea     r8d, [r13+76h]; Size
0x18002477a  lea     rcx, [rsp+1B0h+var_148]; void *
0x18002477f  call    memset_0
0x180024784  xor     r8d, r8d
0x180024787  lea     rdx, [rsp+1B0h+var_170]
0x18002478c  lea     rcx, [rbp+0B0h+var_B0]
0x180024790  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180024795  nop
0x180024796  mov     [rbp+0B0h+arg_0], rsi
0x18002479d  mov     [rbp+0B0h+var_C0], rsi
0x1800247a1  mov     [rbx+2Ch], esi
0x1800247a4  mov     [rbx+40h], esi
0x1800247a7  mov     [rsp+1B0h+var_180], rsi
0x1800247ac  mov     [rsp+1B0h+var_188], sil
0x1800247b1  mov     dword ptr [rsp+1B0h+var_190], esi
0x1800247b5  xor     r9d, r9d
0x1800247b8  mov     r8d, 560038h
0x1800247be  lea     rdx, [rbp+0B0h+var_B0]
0x1800247c2  mov     rcx, rbx
0x1800247c5  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x1800247ca  mov     edi, eax
0x1800247cc  mov     [rbp+0B0h+var_A8], eax
0x1800247cf  test    eax, eax
0x1800247d1  js      loc_180024A06
0x1800247d7  lea     r8, [rbp+0B0h+arg_0]
0x1800247de  lea     rdx, [rbp+0B0h+var_B0]
0x1800247e2  mov     rcx, rbx
0x1800247e5  call    ??$Unpack@_J@CVssIOCTLChannel@@QEAAXAEAVCVssFunctionTracer@@PEA_JK_N@Z; CVssIOCTLChannel::Unpack<__int64>(CVssFunctionTracer &,__int64 *,ulong,bool)
0x1800247ea  mov     rax, [rbp+0B0h+arg_0]
0x1800247f1  mov     rcx, 4000000000000000h
0x1800247fb  test    rcx, rax
0x1800247fe  jz      short loc_18002486E
0x180024800  mov     [rsp+1B0h+var_170], r14
0x180024805  mov     [rsp+1B0h+var_168], r15
0x18002480a  mov     [rsp+1B0h+var_160], r12
0x18002480f  mov     [rsp+1B0h+var_158], 336h
0x180024817  mov     [rsp+1B0h+var_154], r13d
0x18002481c  mov     [rsp+1B0h+var_150], 0FFh
0x180024824  mov     [rbp+0B0h+var_D0], 1000000h
0x18002482b  xor     edx, edx; Val
0x18002482d  lea     r8d, [r13+76h]; Size
0x180024831  lea     rcx, [rsp+1B0h+var_148]; void *
0x180024836  call    memset_0
0x18002483b  lea     r8, aSnapshotVolume; "Snapshot volume is already hidden"
0x180024842  lea     rdx, [rsp+1B0h+var_170]
0x180024847  lea     rcx, [rbp+0B0h+var_B0]
0x18002484b  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180024850  nop
0x180024851  lea     rcx, [rbp+0B0h+var_B0]; this
0x180024855  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18002485a  add     rsp, 178h
0x180024861  pop     r15
0x180024863  pop     r14
0x180024865  pop     r13
0x180024867  pop     r12
0x180024869  pop     rdi
0x18002486a  pop     rsi
0x18002486b  pop     rbx
0x18002486c  pop     rbp
0x18002486d  retn
0x18002486e  or      rax, rcx
0x180024871  mov     [rbp+0B0h+var_C8], rax
0x180024875  mov     [rbx+2Ch], esi
0x180024878  mov     [rbx+40h], esi
0x18002487b  lea     r8, [rbp+0B0h+var_C8]
0x18002487f  lea     rdx, [rbp+0B0h+var_B0]; struct CVssFunctionTracer *
0x180024883  mov     rcx, rbx; this
0x180024886  call    ??$PackArray@U_VOLUME_SET_GPT_ATTRIBUTES_INFORMATION@@@CVssIOCTLChannel@@QEAAPEAXAEAVCVssFunctionTracer@@PEAU_VOLUME_SET_GPT_ATTRIBUTES_INFORMATION@@K@Z; CVssIOCTLChannel::PackArray<_VOLUME_SET_GPT_ATTRIBUTES_INFORMATION>(CVssFunctionTracer &,_VOLUME_SET_GPT_ATTRIBUTES_INFORMATION *,ulong)
0x18002488b  mov     [rsp+1B0h+var_180], rsi
0x180024890  mov     [rsp+1B0h+var_188], sil
0x180024895  mov     dword ptr [rsp+1B0h+var_190], esi
0x180024899  xor     r9d, r9d
0x18002489c  mov     r8d, 560034h
0x1800248a2  lea     rdx, [rbp+0B0h+var_B0]
0x1800248a6  mov     rcx, rbx
0x1800248a9  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x1800248ae  mov     [rbp+0B0h+var_A8], eax
0x1800248b1  mov     rdi, [rbx+68h]
0x1800248b5  shr     eax, 1Fh
0x1800248b8  xor     al, 1
0x1800248ba  mov     [rsp+1B0h+var_170], r14
0x1800248bf  mov     [rsp+1B0h+var_168], r15
0x1800248c4  mov     [rsp+1B0h+var_160], r12
0x1800248c9  mov     [rsp+1B0h+var_154], r13d
0x1800248ce  mov     [rsp+1B0h+var_150], 0FFh
0x1800248d6  mov     [rbp+0B0h+var_D0], 1000000h
0x1800248dd  mov     r8d, 78h ; 'x'; Size
0x1800248e3  lea     rcx, [rsp+1B0h+var_148]; void *
0x1800248e8  jz      short loc_180024916
0x1800248ea  mov     [rsp+1B0h+var_158], 345h
0x1800248f2  xor     edx, edx; Val
0x1800248f4  call    memset_0
0x1800248f9  mov     r9, rdi
0x1800248fc  lea     r8, aHiddenSnapshot; "Hidden snapshot volume %s. "
0x180024903  lea     rdx, [rsp+1B0h+var_170]
0x180024908  lea     rcx, [rbp+0B0h+var_B0]
0x18002490c  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180024911  jmp     loc_180024851
0x180024916  mov     [rsp+1B0h+var_158], 34Ah
0x18002491e  xor     edx, edx; Val
0x180024920  call    memset_0
0x180024925  mov     r9, rdi
0x180024928  lea     r8, aFailToSetGptAt; "Fail to set GPT attributes for %s. Retr"...
0x18002492f  lea     rdx, [rsp+1B0h+var_170]
0x180024934  lea     rcx, [rbp+0B0h+var_B0]
0x180024938  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18002493d  mov     byte ptr [rbp+0B0h+var_C0+1], 1
0x180024941  mov     [rbx+2Ch], esi
0x180024944  mov     [rbx+40h], esi
0x180024947  lea     r8, [rbp+0B0h+var_C8]
0x18002494b  lea     rdx, [rbp+0B0h+var_B0]; struct CVssFunctionTracer *
0x18002494f  mov     rcx, rbx; this
0x180024952  call    ??$PackArray@U_VOLUME_SET_GPT_ATTRIBUTES_INFORMATION@@@CVssIOCTLChannel@@QEAAPEAXAEAVCVssFunctionTracer@@PEAU_VOLUME_SET_GPT_ATTRIBUTES_INFORMATION@@K@Z; CVssIOCTLChannel::PackArray<_VOLUME_SET_GPT_ATTRIBUTES_INFORMATION>(CVssFunctionTracer &,_VOLUME_SET_GPT_ATTRIBUTES_INFORMATION *,ulong)
0x180024957  mov     [rsp+1B0h+var_180], rsi
0x18002495c  mov     [rsp+1B0h+var_188], sil
0x180024961  mov     dword ptr [rsp+1B0h+var_190], esi
0x180024965  xor     r9d, r9d
0x180024968  mov     r8d, 560034h
0x18002496e  lea     rdx, [rbp+0B0h+var_B0]
0x180024972  mov     rcx, rbx
0x180024975  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x18002497a  mov     edi, eax
0x18002497c  mov     [rbp+0B0h+var_A8], eax
0x18002497f  mov     rbx, [rbx+68h]
0x180024983  mov     ecx, eax
0x180024985  shr     ecx, 1Fh
0x180024988  xor     cl, 1
0x18002498b  mov     [rsp+1B0h+var_170], r14
0x180024990  mov     [rsp+1B0h+var_168], r15
0x180024995  mov     [rsp+1B0h+var_160], r12
0x18002499a  mov     [rsp+1B0h+var_154], r13d
0x18002499f  mov     [rsp+1B0h+var_150], 0FFh
0x1800249a7  mov     [rbp+0B0h+var_D0], 1000000h
0x1800249ae  mov     r8d, 78h ; 'x'; Size
0x1800249b4  lea     rcx, [rsp+1B0h+var_148]; void *
0x1800249b9  jz      short loc_1800249D9
0x1800249bb  mov     [rsp+1B0h+var_158], 355h
0x1800249c3  xor     edx, edx; Val
0x1800249c5  call    memset_0
0x1800249ca  mov     r9, rbx
0x1800249cd  lea     r8, aHiddenConnecte; "Hidden connected snapshot volume %s. "
0x1800249d4  jmp     loc_180024903
0x1800249d9  mov     [rsp+1B0h+var_158], 359h
0x1800249e1  xor     edx, edx; Val
0x1800249e3  call    memset_0
0x1800249e8  mov     [rsp+1B0h+var_190], rbx
0x1800249ed  lea     r9, aFailedToHideSn; "Failed to hide snapshot %s"
0x1800249f4  mov     r8d, edi
0x1800249f7  lea     rdx, [rsp+1B0h+var_170]
0x1800249fc  lea     rcx, [rbp+0B0h+var_B0]
0x180024a00  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180024a06  mov     [rsp+1B0h+var_170], r14
0x180024a0b  mov     [rsp+1B0h+var_168], r15
0x180024a10  mov     [rsp+1B0h+var_160], r12
0x180024a15  mov     [rsp+1B0h+var_158], 330h
0x180024a1d  mov     [rsp+1B0h+var_154], r13d
0x180024a22  mov     [rsp+1B0h+var_150], 0FFh
0x180024a2a  mov     [rbp+0B0h+var_D0], 1000000h
0x180024a31  xor     edx, edx; Val
0x180024a33  lea     r8d, [rdx+78h]; Size
0x180024a37  lea     rcx, [rsp+1B0h+var_148]; void *
0x180024a3c  call    memset_0
0x180024a41  mov     rax, [rbx+68h]
0x180024a45  mov     [rsp+1B0h+var_190], rax
0x180024a4a  lea     r9, aCannotFindGptA; "Cannot find GPT attributes for %s"
0x180024a51  mov     r8d, edi
0x180024a54  lea     rdx, [rsp+1B0h+var_170]
0x180024a59  lea     rcx, [rbp+0B0h+var_B0]
0x180024a5d  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
```
