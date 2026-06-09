# CVdsVolume::FormatEx2(ushort *,ushort,ulong,ushort *,ulong,IVdsAsync * *)

- ea: `0x140041710`
- end: `0x140041a73`
- name: `?FormatEx2@CVdsVolume@@UEAAJPEAGGK0KPEAPEAUIVdsAsync@@@Z`
- size: `867`
- prototype: `int(CVdsVolume *__hidden this, unsigned __int16 *, unsigned __int16, unsigned int, unsigned __int16 *, unsigned int, struct IVdsAsync **)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x140003710`
- `0x140004360`
- `0x140004460`
- `0x14002b3f8`
- `0x14002dbd8`
- `0x14002e123`
- `0x140041710`
- `0x1400427c4`
- `0x140044170`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140041a1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140041a1a`
- `vdsutil!RemoveTempVolumeName` at `0x140041a11`
- `vdsutil!RemoveTempVolumeName` at `0x140041a11`
- `vdsutil!VdsHeapFree` at `0x140041a29`
- `vdsutil!VdsHeapFree` at `0x140041a29`
- `vdsutil!VdsTraceEx` at `0x14004183e`
- `vdsutil!VdsTraceEx` at `0x14004183e`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004178a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004178a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140041a42`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140041a42`
- `vdsutil!VdsTraceW` at `0x140041809`
- `vdsutil!VdsTraceW` at `0x140041863`
- `vdsutil!VdsTraceW` at `0x1400419ef`
- `vdsutil!VdsTraceW` at `0x140041809`
- `vdsutil!VdsTraceW` at `0x140041863`
- `vdsutil!VdsTraceW` at `0x1400419ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsVolume::FormatEx2(
        CVdsVolume *this,
        unsigned __int16 *a2,
        unsigned __int16 a3,
        unsigned int a4,
        unsigned __int16 *a5,
        char a6,
        struct IVdsAsync **a7)
{
  signed int v10; // ebx
  const wchar_t *v11; // rax
  char *v12; // rdi
  int v13; // eax
  __int64 v14; // rcx
  const wchar_t *v15; // rdx
  int v16; // eax
  int IsPackOffline; // eax
  int VolumeName; // eax
  __int64 v19; // r8
  bool v20; // r14
  __int64 v21; // rax
  unsigned __int64 v22; // rcx
  int v23; // eax
  HANDLE ProcessHeap; // rax
  int v26; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h] BYREF
  int v29; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v30; // [rsp+78h] [rbp-88h]
  _BYTE v31[16]; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID v32; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID v33; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v34; // [rsp+B0h] [rbp-50h]
  __int128 v35; // [rsp+C0h] [rbp-40h]
  unsigned __int16 *v36; // [rsp+D0h] [rbp-30h]
  unsigned __int16 v38[264]; // [rsp+E0h] [rbp-20h] BYREF

  v27 = a4;
  v30 = a5;
  v26 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v31, 0x5Eu, "CVdsVolume::FormatEx2()");
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  memset_0(v38, 0, 0x208u);
  v28 = 0;
  v29 = 0;
  v10 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v28);
  if ( v10 >= 0 )
  {
    if ( !a7 )
    {
      v10 = -2147024809;
      v11 = a2;
      if ( !a2 )
        v11 = L"UNKNOWN";
      VdsTraceW(0, L"CVdsVolume::FormatEx2, 1, hr=%lX, Type=%p (%s)", 2147942487LL, 0, a2, v11);
      goto LABEL_34;
    }
    *a7 = 0;
    v12 = (char *)this - 40;
    v13 = CVdsVolume::ValidateCall((CVdsVolume *)((char *)this - 40), 8u);
    v10 = v13;
    if ( v13 < 0 )
    {
      VdsTraceEx(94, 0, "CVdsVolume::FormatEx2, 1.5, hr=%lX", v13);
LABEL_34:
      ProcessHeap = GetProcessHeap();
      VdsHeapFree(ProcessHeap, 0, v36);
      v36 = 0;
      goto LABEL_35;
    }
    v14 = *((_QWORD *)this + 11);
    if ( v14 )
    {
      v16 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v14 + 24LL))(v14, &v33);
      v10 = v16;
      if ( v16 < 0 )
      {
        VdsTraceW(0, L"CVdsVolume::FormatEx2, 3, hr=%lX", (unsigned int)v16);
        goto LABEL_34;
      }
      if ( (DWORD2(v35) & 0x1000000) != 0 )
      {
        v10 = -2147210744;
        v15 = L"CVdsVolume::FormatEx2, 4a, hr=%lX";
      }
      else if ( (DWORD2(v35) & 0x1000383) != 0 )
      {
        v10 = -2147210989;
        v15 = L"CVdsVolume::FormatEx2, 4b, hr=%lX";
      }
      else if ( DWORD1(v34) == 5 )
      {
        v10 = -2147212239;
        v15 = L"CVdsVolume::FormatEx2, 5, hr=%lX";
      }
      else
      {
        IsPackOffline = CVdsVolume::IsPackOffline((CVdsVolume *)((char *)this - 40));
        v10 = IsPackOffline;
        if ( IsPackOffline < 0 )
        {
          VdsTraceW(0, L"CVdsVolume::FormatEx2, 6, hr=%lX", (unsigned int)IsPackOffline);
          goto LABEL_34;
        }
        if ( IsPackOffline )
        {
          VolumeName = CVdsVolume::GetVolumeName((CVdsVolume *)((char *)this - 40), v38, &v26, 1, 0, 0);
          v10 = VolumeName;
          if ( VolumeName >= 0 )
          {
            v20 = VolumeName == 1;
            v21 = -1;
            do
              ++v21;
            while ( v38[v21] );
            if ( v38[v21 - 1] == 92 )
            {
              v22 = 2 * v21 - 2;
              if ( v22 >= 0x208 )
                _report_rangecheckfailure(v22, 0, v19);
              *(unsigned __int16 *)((char *)v38 + v22) = 0;
            }
            (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v12 + 8LL))((char *)this - 40, 0);
            v32 = v33;
            v23 = CVdsVolume::FormatInternal(
                    (CVdsVolume *)((char *)this - 40),
                    *((unsigned int **)this + 14),
                    &v32,
                    v36,
                    v20,
                    v36,
                    a2,
                    a3,
                    v27,
                    v30,
                    a6,
                    a7);
            v10 = v23;
            if ( v23 < 0 )
            {
              VdsTraceW(0, L"CVdsVolume::FormatEx2, 9, hr=%lX", (unsigned int)v23);
              (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))((char *)this - 40);
              if ( v20 )
                RemoveTempVolumeName(v38);
            }
          }
          else
          {
            VdsTraceW(0, L"CVdsVolume::FormatEx2, 8, hr=%lX", (unsigned int)VolumeName);
          }
          goto LABEL_34;
        }
        v10 = -2147212220;
        v15 = L"CVdsVolume::FormatEx2, 7, hr=%lX";
      }
    }
    else
    {
      v10 = -2147212216;
      v15 = L"CVdsVolume::FormatEx2, 2, hr=%lX";
    }
    VdsTraceW(0, v15, (unsigned int)v10);
    goto LABEL_34;
  }
LABEL_35:
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v28);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v31);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140041710  push    rbp
0x140041712  push    rbx
0x140041713  push    rsi
0x140041714  push    rdi
0x140041715  push    r12
0x140041717  push    r13
0x140041719  push    r14
0x14004171b  push    r15
0x14004171d  lea     rbp, [rsp-208h]
0x140041725  sub     rsp, 308h
0x14004172c  mov     rax, cs:__security_cookie
0x140041733  xor     rax, rsp
0x140041736  mov     [rbp+240h+var_50], rax
0x14004173d  mov     [rsp+340h+var_2DC], r9d
0x140041742  movzx   r13d, r8w
0x140041746  mov     rsi, rdx
0x140041749  mov     r15, rcx
0x14004174c  mov     rax, [rbp+240h+arg_20]
0x140041753  mov     [rsp+340h+var_2C8], rax
0x140041758  mov     r12, [rbp+240h+arg_30]
0x14004175f  xor     r14d, r14d
0x140041762  mov     [rsp+340h+var_2E0], r14d
0x140041767  xorps   xmm0, xmm0
0x14004176a  xor     eax, eax
0x14004176c  movups  [rbp+240h+var_2A0], xmm0
0x140041770  movups  [rbp+240h+var_290], xmm0
0x140041774  movups  [rbp+240h+var_280], xmm0
0x140041778  mov     [rbp+240h+var_270], rax
0x14004177c  lea     r8, aCvdsvolumeForm_22; "CVdsVolume::FormatEx2()"
0x140041783  lea     edx, [rax+5Eh]
0x140041786  lea     rcx, [rbp+240h+var_2C0]
0x14004178a  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140041790  nop
0x140041791  xorps   xmm0, xmm0
0x140041794  xor     eax, eax
0x140041796  movups  [rbp+240h+var_2A0], xmm0
0x14004179a  movups  [rbp+240h+var_290], xmm0
0x14004179e  movups  [rbp+240h+var_280], xmm0
0x1400417a2  mov     [rbp+240h+var_270], rax
0x1400417a6  xor     edx, edx; Val
0x1400417a8  mov     r8d, 208h; Size
0x1400417ae  lea     rcx, [rbp+240h+var_260]; void *
0x1400417b2  call    memset_0
0x1400417b7  mov     [rsp+340h+var_2D8], r14
0x1400417bc  mov     [rsp+340h+var_2D0], r14d
0x1400417c1  lea     rcx, [rsp+340h+var_2D8]; this
0x1400417c6  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x1400417cb  mov     ebx, eax
0x1400417cd  test    eax, eax
0x1400417cf  js      loc_140041A33
0x1400417d5  test    r12, r12
0x1400417d8  jnz     short loc_140041814
0x1400417da  mov     ebx, 80070057h
0x1400417df  lea     rcx, aUnknown_0; "UNKNOWN"
0x1400417e6  mov     rax, rsi
0x1400417e9  test    rsi, rsi
0x1400417ec  cmovz   rax, rcx
0x1400417f0  mov     [rsp+340h+var_318], rax
0x1400417f5  mov     qword ptr [rsp+340h+var_320], rsi
0x1400417fa  xor     r9d, r9d
0x1400417fd  mov     r8d, ebx
0x140041800  lea     rdx, aCvdsvolumeForm_9; "CVdsVolume::FormatEx2, 1, hr=%lX, Type="...
0x140041807  xor     ecx, ecx
0x140041809  call    cs:__imp_VdsTraceW
0x14004180f  jmp     loc_140041A1A
0x140041814  mov     [r12], r14
0x140041818  lea     rdi, [r15-28h]
0x14004181c  mov     edx, 8; unsigned int
0x140041821  mov     rcx, rdi; this
0x140041824  call    ?ValidateCall@CVdsVolume@@AEAAJK@Z; CVdsVolume::ValidateCall(ulong)
0x140041829  mov     ebx, eax
0x14004182b  test    eax, eax
0x14004182d  jns     short loc_140041849
0x14004182f  mov     r9d, eax
0x140041832  lea     r8, aCvdsvolumeForm_10; "CVdsVolume::FormatEx2, 1.5, hr=%lX"
0x140041839  xor     edx, edx
0x14004183b  lea     ecx, [rdx+5Eh]
0x14004183e  call    cs:__imp_VdsTraceEx
0x140041844  jmp     loc_140041A1A
0x140041849  mov     rcx, [r15+58h]
0x14004184d  test    rcx, rcx
0x140041850  jnz     short loc_14004186E
0x140041852  mov     ebx, 80042448h
0x140041857  lea     rdx, aCvdsvolumeForm_3; "CVdsVolume::FormatEx2, 2, hr=%lX"
0x14004185e  mov     r8d, ebx
0x140041861  xor     ecx, ecx
0x140041863  call    cs:__imp_VdsTraceW
0x140041869  jmp     loc_140041A1A
0x14004186e  mov     rax, [rcx]
0x140041871  lea     rdx, [rbp+240h+var_2A0]
0x140041875  mov     rax, [rax+18h]
0x140041879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004187e  mov     ebx, eax
0x140041880  test    eax, eax
0x140041882  jns     short loc_140041890
0x140041884  mov     r8d, eax
0x140041887  lea     rdx, aCvdsvolumeForm_38; "CVdsVolume::FormatEx2, 3, hr=%lX"
0x14004188e  jmp     short loc_140041861
0x140041890  test    dword ptr [rbp+240h+var_280+8], 1000000h
0x140041897  jz      short loc_1400418A7
0x140041899  mov     ebx, 80042A08h
0x14004189e  lea     rdx, aCvdsvolumeForm_11; "CVdsVolume::FormatEx2, 4a, hr=%lX"
0x1400418a5  jmp     short loc_14004185E
0x1400418a7  test    dword ptr [rbp+240h+var_280+8], 1000383h
0x1400418ae  jz      short loc_1400418BE
0x1400418b0  mov     ebx, 80042913h
0x1400418b5  lea     rdx, aCvdsvolumeForm_1; "CVdsVolume::FormatEx2, 4b, hr=%lX"
0x1400418bc  jmp     short loc_14004185E
0x1400418be  cmp     dword ptr [rbp+240h+var_290+4], 5
0x1400418c2  jnz     short loc_1400418D2
0x1400418c4  mov     ebx, 80042431h
0x1400418c9  lea     rdx, aCvdsvolumeForm_25; "CVdsVolume::FormatEx2, 5, hr=%lX"
0x1400418d0  jmp     short loc_14004185E
0x1400418d2  mov     rcx, rdi; this
0x1400418d5  call    ?IsPackOffline@CVdsVolume@@AEAAJXZ; CVdsVolume::IsPackOffline(void)
0x1400418da  mov     ebx, eax
0x1400418dc  test    eax, eax
0x1400418de  jns     short loc_1400418EF
0x1400418e0  mov     r8d, eax
0x1400418e3  lea     rdx, aCvdsvolumeForm_29; "CVdsVolume::FormatEx2, 6, hr=%lX"
0x1400418ea  jmp     loc_140041861
0x1400418ef  jnz     short loc_140041902
0x1400418f1  mov     ebx, 80042444h
0x1400418f6  lea     rdx, aCvdsvolumeForm_13; "CVdsVolume::FormatEx2, 7, hr=%lX"
0x1400418fd  jmp     loc_14004185E
0x140041902  mov     [rsp+340h+var_318], r14; unsigned __int16 *
0x140041907  mov     [rsp+340h+var_320], r14d; unsigned int
0x14004190c  mov     r9d, 1; int
0x140041912  lea     r8, [rsp+340h+var_2E0]; int *
0x140041917  lea     rdx, [rbp+240h+var_260]; unsigned __int16 *
0x14004191b  mov     rcx, rdi; this
0x14004191e  call    ?GetVolumeName@CVdsVolume@@AEAAJQEAGPEAHHKPEAG@Z; CVdsVolume::GetVolumeName(ushort * const,int *,int,ulong,ushort *)
0x140041923  mov     ebx, eax
0x140041925  test    eax, eax
0x140041927  jns     short loc_140041938
0x140041929  mov     r8d, eax
0x14004192c  lea     rdx, aCvdsvolumeForm_37; "CVdsVolume::FormatEx2, 8, hr=%lX"
0x140041933  jmp     loc_140041861
0x140041938  cmp     eax, 1
0x14004193b  setz    r14b
0x14004193f  lea     rcx, [rbp+240h+var_260]
0x140041943  or      rax, 0FFFFFFFFFFFFFFFFh
0x140041947  xor     edx, edx
0x140041949  inc     rax
0x14004194c  cmp     [rcx+rax*2], dx
0x140041950  jnz     short loc_140041949
0x140041952  mov     ecx, 5Ch ; '\'
0x140041957  cmp     cx, [rbp+rax*2+240h+var_262]
0x14004195c  jnz     short loc_140041978
0x14004195e  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x140041966  cmp     rcx, 208h
0x14004196d  jnb     loc_140041A6D
0x140041973  mov     [rbp+rcx+240h+var_260], dx
0x140041978  mov     rax, [rdi]
0x14004197b  mov     rcx, rdi
0x14004197e  mov     rax, [rax+8]
0x140041982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041987  movups  xmm0, [rbp+240h+var_2A0]
0x14004198b  movdqu  xmmword ptr [rbp+240h+var_2B0.Data1], xmm0
0x140041990  movzx   ecx, r14b
0x140041994  mov     [rsp+340h+var_2E8], r12; struct IVdsAsync **
0x140041999  mov     eax, dword ptr [rbp+240h+arg_28]
0x14004199f  mov     [rsp+340h+var_2F0], eax; unsigned int
0x1400419a3  mov     rax, [rsp+340h+var_2C8]
0x1400419a8  mov     [rsp+340h+var_2F8], rax; unsigned __int16 *
0x1400419ad  mov     eax, [rsp+340h+var_2DC]
0x1400419b1  mov     [rsp+340h+var_300], eax; unsigned int
0x1400419b5  mov     [rsp+340h+var_308], r13w; unsigned __int16
0x1400419bb  mov     [rsp+340h+String1], rsi; String1
0x1400419c0  mov     r9, [rbp+240h+var_270]; unsigned __int16 *
0x1400419c4  mov     [rsp+340h+var_318], r9; unsigned __int16 *
0x1400419c9  mov     [rsp+340h+var_320], ecx; int
0x1400419cd  lea     r8, [rbp+240h+var_2B0]; struct _GUID *
0x1400419d1  mov     rdx, [r15+70h]; unsigned int *
0x1400419d5  mov     rcx, rdi; struct CVdsVolume *
0x1400419d8  call    ?FormatInternal@CVdsVolume@@SAJPEAV1@PEAKU_GUID@@PEAGH33GK3KPEAPEAUIVdsAsync@@@Z; CVdsVolume::FormatInternal(CVdsVolume *,ulong *,_GUID,ushort *,int,ushort *,ushort *,ushort,ulong,ushort *,ulong,IVdsAsync * *)
0x1400419dd  mov     ebx, eax
0x1400419df  test    eax, eax
0x1400419e1  jns     short loc_140041A17
0x1400419e3  mov     r8d, eax
0x1400419e6  lea     rdx, aCvdsvolumeForm_2; "CVdsVolume::FormatEx2, 9, hr=%lX"
0x1400419ed  xor     ecx, ecx
0x1400419ef  call    cs:__imp_VdsTraceW
0x1400419f5  mov     rax, [rdi]
0x1400419f8  mov     rcx, rdi
0x1400419fb  mov     rax, [rax+10h]
0x1400419ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041a04  test    r14b, r14b
0x140041a07  jz      short loc_140041A17
0x140041a09  mov     rdx, [rbp+240h+var_270]
0x140041a0d  lea     rcx, [rbp+240h+var_260]
0x140041a11  call    cs:__imp_RemoveTempVolumeName
0x140041a17  xor     r14d, r14d
0x140041a1a  call    cs:__imp_GetProcessHeap
0x140041a20  mov     rcx, rax
0x140041a23  mov     r8, [rbp+240h+var_270]
0x140041a27  xor     edx, edx
0x140041a29  call    cs:__imp_VdsHeapFree
0x140041a2f  mov     [rbp+240h+var_270], r14
0x140041a33  lea     rcx, [rsp+340h+var_2D8]; this
0x140041a38  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140041a3d  nop
0x140041a3e  lea     rcx, [rbp+240h+var_2C0]
0x140041a42  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140041a48  mov     eax, ebx
0x140041a4a  mov     rcx, [rbp+240h+var_50]
0x140041a51  xor     rcx, rsp; StackCookie
0x140041a54  call    __security_check_cookie
0x140041a59  add     rsp, 308h
0x140041a60  pop     r15
0x140041a62  pop     r14
0x140041a64  pop     r13
0x140041a66  pop     r12
0x140041a68  pop     rdi
0x140041a69  pop     rsi
0x140041a6a  pop     rbx
0x140041a6b  pop     rbp
0x140041a6c  retn
0x140041a6d  call    __report_rangecheckfailure
```
