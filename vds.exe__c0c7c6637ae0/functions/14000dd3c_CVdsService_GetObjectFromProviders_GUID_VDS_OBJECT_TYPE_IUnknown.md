# CVdsService::GetObjectFromProviders(_GUID,_VDS_OBJECT_TYPE,IUnknown * *)

- ea: `0x14000dd3c`
- end: `0x14000dfac`
- name: `?GetObjectFromProviders@CVdsService@@SAJU_GUID@@W4_VDS_OBJECT_TYPE@@PEAPEAUIUnknown@@@Z`
- size: `624`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, enum _VDS_OBJECT_TYPE, struct IUnknown **)`
- caller_count: `13`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140004d80`
- `0x140005630`
- `0x14000e920`
- `0x14000ff10`
- `0x140013620`
- `0x140038c64`
- `0x1400392a0`
- `0x140039984`
- `0x14003a2dc`
- `0x14003b910`
- `0x14003f700`
- `0x14003fea0`
- `0x140040808`

## callees

- `0x14000dd3c`
- `0x140052e46`
- `0x140056010`

## import_xrefs

- `vdsutil!VdsTraceEx` at `0x14000df43`
- `vdsutil!VdsTraceEx` at `0x14000df7a`
- `vdsutil!VdsTraceEx` at `0x14000df43`
- `vdsutil!VdsTraceEx` at `0x14000df7a`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14000de05`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14000de05`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14000de1a`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14000de1a`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14000de47`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14000de47`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14000df4d`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14000df4d`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000dd80`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000dd80`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000df94`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000df94`
- `vdsutil!VdsTraceW` at `0x14000dda1`
- `vdsutil!VdsTraceW` at `0x14000dda1`

## string_xrefs

- `0x14000de70`: `CVdsService::GetObjectFromProviders, 3, %lX`
- `0x14000dd70`: `CVdsService::GetObjectFromProviders()`
- `0x14000dd8c`: `CVdsService::GetObjectFromProviders, 1, hr=%lX`
- `0x14000dec8`: `CVdsService::GetObjectFromProviders, 2, hr=%lX`
- `0x14000df6e`: `CVdsService::GetObjectFromProviders, 4, %lX`
- `0x14000df37`: `CVdsService::GetObjectFromProviders, 5, %lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsService::GetObjectFromProviders(struct _GUID *a1, unsigned int a2, struct IUnknown **a3)
{
  const wchar_t *v6; // rdx
  int v7; // ebx
  __int64 *v8; // rsi
  __int64 (__fastcall ***EntryPointer)(void *, GUID *, __int64 *); // rax
  int v10; // eax
  __int64 v12; // [rsp+30h] [rbp-29h] BYREF
  struct IUnknown *v13; // [rsp+38h] [rbp-21h] BYREF
  __int128 Buf1; // [rsp+40h] [rbp-19h] BYREF
  __int128 Buf2; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v16[16]; // [rsp+60h] [rbp+7h] BYREF
  _BYTE v17[64]; // [rsp+70h] [rbp+17h] BYREF

  v12 = 0;
  v13 = 0;
  Buf1 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v16, 0x5Eu, "CVdsService::GetObjectFromProviders()");
  if ( !a3 )
  {
    v6 = L"CVdsService::GetObjectFromProviders, 1, hr=%lX";
LABEL_3:
    v7 = -2147212216;
    VdsTraceW(0, v6, 2147755080LL);
    goto LABEL_40;
  }
  *a3 = 0;
  if ( (int)a2 > 33 )
  {
    if ( a2 == 34 || a2 == 35 || a2 == 36 || a2 == 37 || a2 == 38 || a2 == 39 )
      goto LABEL_12;
    if ( a2 == 200 )
    {
      v8 = CVdsService::m_lstVirtualDiskProviders;
      goto LABEL_13;
    }
LABEL_25:
    v6 = L"CVdsService::GetObjectFromProviders, 2, hr=%lX";
    goto LABEL_3;
  }
  if ( a2 != 33 )
  {
    if ( a2 == 10 || a2 == 11 || a2 == 12 || a2 == 13 )
    {
      v8 = CVdsService::m_lstSoftwareProviders;
      goto LABEL_13;
    }
    if ( a2 != 30 && a2 - 31 > 1 )
      goto LABEL_25;
  }
LABEL_12:
  v8 = CVdsService::m_lstHardwareProviders;
LABEL_13:
  for ( Buf1 = *(_OWORD *)CRtlList::Begin(v8, &Buf2); ; CRtlListIter::Next((CRtlListIter *)&Buf1) )
  {
    Buf2 = *(_OWORD *)CRtlList::End(v8, v17);
    if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
    {
      v7 = 0;
      goto LABEL_38;
    }
    EntryPointer = (__int64 (__fastcall ***)(void *, GUID *, __int64 *))CRtlListIter::GetEntryPointer((CRtlListIter *)&Buf1);
    v10 = (**EntryPointer)(EntryPointer, &IID_IVdsProviderPrivate, &v12);
    if ( v10 < 0 )
    {
      VdsTraceEx(94, 0, "CVdsService::GetObjectFromProviders, 3, %lX", (unsigned int)v10);
      continue;
    }
    if ( !v12 )
    {
      v7 = -2147212216;
      VdsTraceEx(94, 0, "CVdsService::GetObjectFromProviders, 4, %lX", -2147212216);
      goto LABEL_40;
    }
    Buf2 = (__int128)*a1;
    v7 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, struct IUnknown **))(*(_QWORD *)v12 + 24LL))(
           v12,
           &Buf2,
           a2,
           &v13);
    if ( v12 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      v12 = 0;
    }
    if ( v7 != -2147212283 )
      break;
LABEL_33:
    ;
  }
  if ( v7 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsService::GetObjectFromProviders, 5, %lX", (unsigned int)v7);
    goto LABEL_33;
  }
  *a3 = v13;
  if ( v7 )
    goto LABEL_40;
LABEL_38:
  if ( !*a3 )
    v7 = -2147212283;
LABEL_40:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v16);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000dd3c  push    rbp
0x14000dd3e  push    rbx
0x14000dd3f  push    rsi
0x14000dd40  push    rdi
0x14000dd41  push    r14
0x14000dd43  push    r15
0x14000dd45  lea     rbp, [rsp-2Fh]
0x14000dd4a  sub     rsp, 88h
0x14000dd51  mov     r14, r8
0x14000dd54  mov     edi, edx
0x14000dd56  mov     r15, rcx
0x14000dd59  mov     [rbp+57h+var_80], 0
0x14000dd61  mov     [rbp+57h+var_78], 0
0x14000dd69  xorps   xmm0, xmm0
0x14000dd6c  movups  [rbp+57h+Buf1], xmm0
0x14000dd70  lea     r8, aCvdsserviceGet_84; "CVdsService::GetObjectFromProviders()"
0x14000dd77  mov     edx, 5Eh ; '^'
0x14000dd7c  lea     rcx, [rbp+57h+var_50]
0x14000dd80  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000dd86  nop
0x14000dd87  test    r14, r14
0x14000dd8a  jnz     short loc_14000DDAC
0x14000dd8c  lea     rdx, aCvdsserviceGet_4; "CVdsService::GetObjectFromProviders, 1,"...
0x14000dd93  mov     r9d, 80042448h
0x14000dd99  mov     r8d, r9d
0x14000dd9c  mov     ebx, r9d
0x14000dd9f  xor     ecx, ecx
0x14000dda1  call    cs:__imp_VdsTraceW
0x14000dda7  jmp     loc_14000DF90
0x14000ddac  mov     qword ptr [r14], 0
0x14000ddb3  cmp     edi, 21h ; '!'
0x14000ddb6  jg      loc_14000DE88
0x14000ddbc  jz      short loc_14000DDF7
0x14000ddbe  mov     ecx, edi
0x14000ddc0  sub     ecx, 0Ah
0x14000ddc3  jz      loc_14000DE7C
0x14000ddc9  sub     ecx, 1
0x14000ddcc  jz      loc_14000DE7C
0x14000ddd2  sub     ecx, 1
0x14000ddd5  jz      loc_14000DE7C
0x14000dddb  sub     ecx, 1
0x14000ddde  jz      loc_14000DE7C
0x14000dde4  sub     ecx, 11h
0x14000dde7  jz      short loc_14000DDF7
0x14000dde9  sub     ecx, 1
0x14000ddec  jz      short loc_14000DDF7
0x14000ddee  cmp     ecx, 1
0x14000ddf1  jnz     loc_14000DEC8
0x14000ddf7  lea     rsi, ?m_lstHardwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstHardwareProviders
0x14000ddfe  lea     rdx, [rbp+57h+Buf2]
0x14000de02  mov     rcx, rsi
0x14000de05  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x14000de0b  movups  xmm0, xmmword ptr [rax]
0x14000de0e  movdqu  [rbp+57h+Buf1], xmm0
0x14000de13  lea     rdx, [rbp+57h+var_40]
0x14000de17  mov     rcx, rsi
0x14000de1a  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x14000de20  movups  xmm0, xmmword ptr [rax]
0x14000de23  movdqu  [rbp+57h+Buf2], xmm0
0x14000de28  mov     r8d, 10h; Size
0x14000de2e  lea     rdx, [rbp+57h+Buf2]; Buf2
0x14000de32  lea     rcx, [rbp+57h+Buf1]; Buf1
0x14000de36  call    memcmp_0
0x14000de3b  test    eax, eax
0x14000de3d  jz      loc_14000DF82
0x14000de43  lea     rcx, [rbp+57h+Buf1]
0x14000de47  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x14000de4d  mov     r9, rax
0x14000de50  mov     rcx, [rax]
0x14000de53  mov     rax, [rcx]
0x14000de56  lea     r8, [rbp+57h+var_80]
0x14000de5a  lea     rdx, IID_IVdsProviderPrivate
0x14000de61  mov     rcx, r9
0x14000de64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000de69  test    eax, eax
0x14000de6b  jns     short loc_14000DEE0
0x14000de6d  mov     r9d, eax
0x14000de70  lea     r8, aCvdsserviceGet_118; "CVdsService::GetObjectFromProviders, 3,"...
0x14000de77  jmp     loc_14000DF3E
0x14000de7c  lea     rsi, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstSoftwareProviders
0x14000de83  jmp     loc_14000DDFE
0x14000de88  mov     ecx, edi
0x14000de8a  sub     ecx, 22h ; '"'
0x14000de8d  jz      loc_14000DDF7
0x14000de93  sub     ecx, 1
0x14000de96  jz      loc_14000DDF7
0x14000de9c  sub     ecx, 1
0x14000de9f  jz      loc_14000DDF7
0x14000dea5  sub     ecx, 1
0x14000dea8  jz      loc_14000DDF7
0x14000deae  sub     ecx, 1
0x14000deb1  jz      loc_14000DDF7
0x14000deb7  sub     ecx, 1
0x14000deba  jz      loc_14000DDF7
0x14000dec0  cmp     ecx, 0A1h
0x14000dec6  jz      short loc_14000DED4
0x14000dec8  lea     rdx, aCvdsserviceGet_59; "CVdsService::GetObjectFromProviders, 2,"...
0x14000decf  jmp     loc_14000DD93
0x14000ded4  lea     rsi, ?m_lstVirtualDiskProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstVirtualDiskProviders
0x14000dedb  jmp     loc_14000DDFE
0x14000dee0  mov     rcx, [rbp+57h+var_80]
0x14000dee4  test    rcx, rcx
0x14000dee7  jz      short loc_14000DF65
0x14000dee9  movaps  xmm0, xmmword ptr [r15]
0x14000deed  movdqa  [rbp+57h+Buf2], xmm0
0x14000def2  mov     rax, [rcx]
0x14000def5  lea     r9, [rbp+57h+var_78]
0x14000def9  mov     r8d, edi
0x14000defc  lea     rdx, [rbp+57h+Buf2]
0x14000df00  mov     rax, [rax+18h]
0x14000df04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000df09  mov     ebx, eax
0x14000df0b  mov     rcx, [rbp+57h+var_80]
0x14000df0f  test    rcx, rcx
0x14000df12  jz      short loc_14000DF28
0x14000df14  mov     rdx, [rcx]
0x14000df17  mov     rax, [rdx+10h]
0x14000df1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000df20  mov     [rbp+57h+var_80], 0
0x14000df28  cmp     ebx, 80042405h
0x14000df2e  jz      short loc_14000DF49
0x14000df30  test    ebx, ebx
0x14000df32  jns     short loc_14000DF58
0x14000df34  mov     r9d, ebx
0x14000df37  lea     r8, aCvdsserviceGet_116; "CVdsService::GetObjectFromProviders, 5,"...
0x14000df3e  xor     edx, edx
0x14000df40  lea     ecx, [rdx+5Eh]
0x14000df43  call    cs:__imp_VdsTraceEx
0x14000df49  lea     rcx, [rbp+57h+Buf1]
0x14000df4d  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x14000df53  jmp     loc_14000DE13
0x14000df58  mov     rax, [rbp+57h+var_78]
0x14000df5c  mov     [r14], rax
0x14000df5f  test    ebx, ebx
0x14000df61  jz      short loc_14000DF84
0x14000df63  jmp     short loc_14000DF90
0x14000df65  mov     r9d, 80042448h
0x14000df6b  mov     ebx, r9d
0x14000df6e  lea     r8, aCvdsserviceGet_26; "CVdsService::GetObjectFromProviders, 4,"...
0x14000df75  xor     edx, edx
0x14000df77  lea     ecx, [rdx+5Eh]
0x14000df7a  call    cs:__imp_VdsTraceEx
0x14000df80  jmp     short loc_14000DF90
0x14000df82  xor     ebx, ebx
0x14000df84  cmp     qword ptr [r14], 0
0x14000df88  mov     eax, 80042405h
0x14000df8d  cmovz   ebx, eax
0x14000df90  lea     rcx, [rbp+57h+var_50]
0x14000df94  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000df9a  mov     eax, ebx
0x14000df9c  add     rsp, 88h
0x14000dfa3  pop     r15
0x14000dfa5  pop     r14
0x14000dfa7  pop     rdi
0x14000dfa8  pop     rsi
0x14000dfa9  pop     rbx
0x14000dfaa  pop     rbp
0x14000dfab  retn
```
