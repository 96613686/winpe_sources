# CUsbPdoFilter::Initialize(WDFDEVICE__ *,_DEVICE_OBJECT *,_GUID *,_EPROCESS *,ushort const *)

- ea: `0x140005754`
- end: `0x140005a4b`
- name: `?Initialize@CUsbPdoFilter@@AEAAJPEAUWDFDEVICE__@@PEAU_DEVICE_OBJECT@@PEAU_GUID@@PEAU_EPROCESS@@PEBG@Z`
- size: `759`
- prototype: `__int64 __usercall@<rax>(CUsbPdoFilter *__hidden this@<rcx>, struct WDFDEVICE__ *@<rdx>, struct _DEVICE_OBJECT *@<r8>, struct _GUID *@<r9>, struct _EPROCESS *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400051b4`

## callees

- `0x140004f48`
- `0x140005754`
- `0x140005e44`
- `0x1400060dc`
- `0x140006128`
- `0x14000a2e8`
- `0x14000aa30`
- `0x14000ab00`
- `0x14000b140`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByPointer` at `0x1400058eb`
- `ntoskrnl!ObReferenceObjectByPointer` at `0x1400058eb`
- `ntoskrnl!PsProcessType` at `0x1400058d9`
- `ntoskrnl!ExAllocatePool2` at `0x140005953`
- `ntoskrnl!ExAllocatePool2` at `0x140005953`

## pseudocode

```c
__int64 __fastcall CUsbPdoFilter::Initialize(
        CUsbPdoFilter *this,
        struct WDFDEVICE__ *a2,
        struct _DEVICE_OBJECT *a3,
        struct _GUID *a4,
        struct _EPROCESS *Object,
        STRSAFE_PCNZWCH psz)
{
  __int64 v10; // rax
  __int128 v11; // xmm0
  __int64 v12; // rdx
  NTSTATUS v13; // ebx
  PDEVICE_OBJECT v14; // rcx
  unsigned __int16 v15; // dx
  struct _EPROCESS *v16; // rdi
  const wchar_t *v17; // r14
  size_t v18; // rdi
  size_t v19; // rax
  void *Pool2; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int128 v24; // [rsp+30h] [rbp-79h] BYREF
  __int128 v25; // [rsp+40h] [rbp-69h]
  __int128 v26; // [rsp+50h] [rbp-59h]
  __int64 v27; // [rsp+60h] [rbp-49h]
  _QWORD v28[16]; // [rsp+70h] [rbp-39h] BYREF
  size_t pcchLength; // [rsp+100h] [rbp+57h] BYREF
  __int64 v30; // [rsp+108h] [rbp+5Fh] BYREF

  memset(v28, 0, 0x60u);
  *(_QWORD *)this = a2;
  v27 = 0;
  pcchLength = 0;
  v30 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v10 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFDEVICE__ *))WPP_MAIN_CB.Queue.ListEntry.Flink[15].Blink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          a2);
  v11 = (__int128)*a4;
  *(_BYTE *)(v10 + 76) = a3->StackSize + 1;
  *((_OWORD *)this + 1) = v11;
  memset(v28, 0, 0x60u);
  v12 = *(_QWORD *)this;
  v28[5] = &PfEvtIoDeviceControl;
  v28[0] = 0x200000060LL;
  *(_QWORD *)&v25 = 0;
  BYTE5(v28[1]) = 1;
  v24 = 0;
  LODWORD(v28[1]) = 2;
  v28[6] = &PfEvtIoInternalDeviceControl;
  v27 = 0;
  LODWORD(v28[10]) = -1;
  v26 = 0;
  LODWORD(v24) = 56;
  *((_QWORD *)&v25 + 1) = 0x400000002LL;
  v13 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, _QWORD *, __int128 *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[76].Flink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          v12,
          v28,
          &v24,
          &v30);
  if ( v13 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v15 = 16;
LABEL_5:
      WPP_SF_d((__int64)v14->AttachedDevice, v15, (__int64)WPP_be851031edc93d18f2bbe38844c4b0c7_Traceguids, v13);
      return (unsigned int)v13;
    }
    return (unsigned int)v13;
  }
  v13 = CUsbPdoFilter::PdoAttach(this, a3);
  if ( v13 < 0 )
    return (unsigned int)v13;
  v16 = Object;
  if ( !Object )
  {
    v13 = -1073741823;
    goto LABEL_23;
  }
  v13 = ObReferenceObjectByPointer(Object, 0, (POBJECT_TYPE)PsProcessType, 0);
  if ( v13 < 0 )
  {
LABEL_23:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_be851031edc93d18f2bbe38844c4b0c7_Traceguids, v16, v13);
    return (unsigned int)v13;
  }
  v17 = psz;
  *((_QWORD *)this + 4) = v16;
  if ( v17 )
  {
    v13 = RtlStringLengthWorkerW(v17, 0xFFFFu, &pcchLength);
    if ( v13 >= 0 )
    {
      v18 = pcchLength + 1;
      v19 = 2 * (pcchLength + 1);
      if ( !is_mul_ok(pcchLength + 1, 2u) )
        v19 = -1;
      Pool2 = (void *)ExAllocatePool2(256, v19, 1917088324);
      *((_QWORD *)this + 1) = Pool2;
      if ( Pool2 )
      {
        memmove(Pool2, v17, 2 * v18);
        ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[13].Blink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          *(_QWORD *)this);
        return 0;
      }
      else
      {
        v13 = -1073741801;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_I(WPP_GLOBAL_Control->AttachedDevice, v21, v22, v18);
      }
      return (unsigned int)v13;
    }
  }
  else
  {
    v13 = -1073741811;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v15 = 18;
    goto LABEL_5;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140005754  mov     [rsp-8+arg_10], rbx
0x140005759  push    rbp
0x14000575a  push    rsi
0x14000575b  push    rdi
0x14000575c  push    r14
0x14000575e  push    r15
0x140005760  lea     rbp, [rsp-27h]
0x140005765  sub     rsp, 0D0h
0x14000576c  mov     r14, r8
0x14000576f  mov     rbx, rdx
0x140005772  mov     rsi, rcx
0x140005775  mov     r15d, 60h ; '`'
0x14000577b  mov     r8d, r15d; Size
0x14000577e  lea     rcx, [rbp+47h+var_80]; void *
0x140005782  xor     edx, edx; Val
0x140005784  mov     rdi, r9
0x140005787  call    memset
0x14000578c  xor     eax, eax
0x14000578e  mov     [rsi], rbx
0x140005791  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140005798  xorps   xmm0, xmm0
0x14000579b  mov     [rbp+47h+var_90], rax
0x14000579f  mov     rdx, rbx
0x1400057a2  mov     [rbp+47h+pcchLength], rax
0x1400057a6  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400057ad  mov     [rbp+47h+arg_8], 0
0x1400057b5  movups  [rbp+47h+var_C0], xmm0
0x1400057b9  movups  [rbp+47h+var_B0], xmm0
0x1400057bd  movups  [rbp+47h+var_A0], xmm0
0x1400057c1  mov     rax, [rax+0F8h]
0x1400057c8  call    _guard_dispatch_icall
0x1400057cd  mov     cl, [r14+4Ch]
0x1400057d1  mov     r8d, r15d; Size
0x1400057d4  movups  xmm0, xmmword ptr [rdi]
0x1400057d7  inc     cl
0x1400057d9  xor     edx, edx; Val
0x1400057db  mov     [rax+4Ch], cl
0x1400057de  lea     rcx, [rbp+47h+var_80]; void *
0x1400057e2  movdqu  xmmword ptr [rsi+10h], xmm0
0x1400057e7  call    memset
0x1400057ec  mov     rdx, [rsi]
0x1400057ef  lea     rax, PfEvtIoDeviceControl
0x1400057f6  mov     [rbp+47h+var_58], rax
0x1400057fa  lea     rcx, [rbp+47h+arg_8]
0x1400057fe  xorps   xmm0, xmm0
0x140005801  mov     [rbp+47h+var_80], r15d
0x140005805  movups  [rbp+47h+var_B0], xmm0
0x140005809  mov     r15d, 2
0x14000580f  mov     [rbp+47h+var_73], 1
0x140005813  movups  [rbp+47h+var_C0], xmm0
0x140005817  lea     rax, PfEvtIoInternalDeviceControl
0x14000581e  mov     [rbp+47h+var_78], r15d
0x140005822  mov     [rbp+47h+var_50], rax
0x140005826  lea     r9, [rbp+47h+var_C0]
0x14000582a  xor     eax, eax
0x14000582c  mov     [rbp+47h+var_7C], r15d
0x140005830  mov     [rbp+47h+var_90], rax
0x140005834  lea     r8, [rbp+47h+var_80]
0x140005838  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000583f  mov     [rbp+47h+var_30], 0FFFFFFFFh
0x140005846  movups  [rbp+47h+var_A0], xmm0
0x14000584a  mov     dword ptr [rbp+47h+var_C0], 38h ; '8'
0x140005851  mov     dword ptr [rbp+47h+var_B0+8], r15d
0x140005855  mov     dword ptr [rbp+47h+var_B0+0Ch], 4
0x14000585c  mov     rax, [rax+4C0h]
0x140005863  mov     [rsp+0F0h+var_D0], rcx
0x140005868  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000586f  call    _guard_dispatch_icall
0x140005874  mov     ebx, eax
0x140005876  test    eax, eax
0x140005878  jns     short loc_1400058B7
0x14000587a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005881  lea     rax, WPP_GLOBAL_Control
0x140005888  cmp     rcx, rax
0x14000588b  jz      loc_140005A31
0x140005891  cmp     [rcx+29h], r15b
0x140005895  jb      loc_140005A31
0x14000589b  lea     edx, [r15+0Eh]
0x14000589f  mov     rcx, [rcx+18h]
0x1400058a3  lea     r8, WPP_be851031edc93d18f2bbe38844c4b0c7_Traceguids
0x1400058aa  mov     r9d, ebx
0x1400058ad  call    WPP_SF_d
0x1400058b2  jmp     loc_140005A31
0x1400058b7  mov     rdx, r14; struct _DEVICE_OBJECT *
0x1400058ba  mov     rcx, rsi; this
0x1400058bd  call    ?PdoAttach@CUsbPdoFilter@@AEAAJPEAU_DEVICE_OBJECT@@@Z; CUsbPdoFilter::PdoAttach(_DEVICE_OBJECT *)
0x1400058c2  mov     ebx, eax
0x1400058c4  test    eax, eax
0x1400058c6  js      loc_140005A31
0x1400058cc  mov     rdi, [rbp+47h+Object]
0x1400058d0  test    rdi, rdi
0x1400058d3  jz      loc_1400059F7
0x1400058d9  mov     r8, cs:__imp_PsProcessType
0x1400058e0  xor     r9d, r9d; AccessMode
0x1400058e3  xor     edx, edx; DesiredAccess
0x1400058e5  mov     rcx, rdi; Object
0x1400058e8  mov     r8, [r8]; ObjectType
0x1400058eb  call    cs:__imp_ObReferenceObjectByPointer
0x1400058f2  nop     dword ptr [rax+rax+00h]
0x1400058f7  mov     ebx, eax
0x1400058f9  test    eax, eax
0x1400058fb  js      loc_1400059FC
0x140005901  mov     r14, [rbp+47h+psz]
0x140005905  mov     [rsi+20h], rdi
0x140005909  test    r14, r14
0x14000590c  jz      loc_1400059CF
0x140005912  lea     r8, [rbp+47h+pcchLength]; pcchLength
0x140005916  mov     edx, 0FFFFh; cchMax
0x14000591b  mov     rcx, r14; psz
0x14000591e  call    RtlStringLengthWorkerW
0x140005923  mov     ebx, eax
0x140005925  test    eax, eax
0x140005927  js      loc_1400059D4
0x14000592d  mov     rdi, [rbp+47h+pcchLength]
0x140005931  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140005938  inc     rdi
0x14000593b  mov     rax, r15
0x14000593e  mul     rdi
0x140005941  mov     r8d, 72447244h
0x140005947  cmovb   rax, rcx
0x14000594b  mov     ecx, 100h
0x140005950  mov     rdx, rax
0x140005953  call    cs:__imp_ExAllocatePool2
0x14000595a  nop     dword ptr [rax+rax+00h]
0x14000595f  mov     [rsi+8], rax
0x140005963  test    rax, rax
0x140005966  jnz     short loc_14000599F
0x140005968  mov     ebx, 0C0000017h
0x14000596d  mov     rcx, cs:WPP_GLOBAL_Control
0x140005974  lea     rax, WPP_GLOBAL_Control
0x14000597b  cmp     rcx, rax
0x14000597e  jz      loc_140005A31
0x140005984  cmp     [rcx+29h], r15b
0x140005988  jb      loc_140005A31
0x14000598e  mov     rcx, [rcx+18h]
0x140005992  mov     r9, rdi
0x140005995  call    WPP_SF_I
0x14000599a  jmp     loc_140005A31
0x14000599f  lea     r8, [rdi+rdi]; Size
0x1400059a3  mov     rdx, r14; Src
0x1400059a6  mov     rcx, rax; void *
0x1400059a9  call    memmove
0x1400059ae  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400059b5  mov     rdx, [rsi]
0x1400059b8  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400059bf  mov     rax, [rax+0D8h]
0x1400059c6  call    _guard_dispatch_icall
0x1400059cb  xor     ebx, ebx
0x1400059cd  jmp     short loc_140005A31
0x1400059cf  mov     ebx, 0C000000Dh
0x1400059d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400059db  lea     rax, WPP_GLOBAL_Control
0x1400059e2  cmp     rcx, rax
0x1400059e5  jz      short loc_140005A31
0x1400059e7  cmp     [rcx+29h], r15b
0x1400059eb  jb      short loc_140005A31
0x1400059ed  mov     edx, 12h
0x1400059f2  jmp     loc_14000589F
0x1400059f7  mov     ebx, 0C0000001h
0x1400059fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a03  lea     rax, WPP_GLOBAL_Control
0x140005a0a  cmp     rcx, rax
0x140005a0d  jz      short loc_140005A31
0x140005a0f  cmp     [rcx+29h], r15b
0x140005a13  jb      short loc_140005A31
0x140005a15  mov     rcx, [rcx+18h]
0x140005a19  lea     r8, WPP_be851031edc93d18f2bbe38844c4b0c7_Traceguids
0x140005a20  mov     edx, 11h
0x140005a25  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x140005a29  mov     r9, rdi
0x140005a2c  call    WPP_SF_qd
0x140005a31  mov     eax, ebx
0x140005a33  mov     rbx, [rsp+0F0h+arg_10]
0x140005a3b  add     rsp, 0D0h
0x140005a42  pop     r15
0x140005a44  pop     r14
0x140005a46  pop     rdi
0x140005a47  pop     rsi
0x140005a48  pop     rbp
0x140005a49  retn
```
