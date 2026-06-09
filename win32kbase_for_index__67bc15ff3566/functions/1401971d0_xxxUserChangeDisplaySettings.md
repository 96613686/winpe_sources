# xxxUserChangeDisplaySettings

- ea: `0x1401971d0`
- end: `0x140197a79`
- name: `xxxUserChangeDisplaySettings`
- size: `2217`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task`

## callers

- `0x1401d95d0`

## callees

- `0x140003e34`
- `0x140004030`
- `0x14004dd98`
- `0x14004dfb0`
- `0x140070518`
- `0x14007b930`
- `0x14007df80`
- `0x14007efd0`
- `0x14016f7a0`
- `0x140196d30`
- `0x1401971d0`
- `0x1401bf420`
- `0x1402388e0`
- `0x140238f80`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401972bd`
- `ntoskrnl!ProbeForRead` at `0x14019738a`
- `ntoskrnl!ProbeForRead` at `0x140197455`
- `ntoskrnl!ProbeForRead` at `0x140197544`
- `ntoskrnl!ProbeForRead` at `0x1401972bd`
- `ntoskrnl!ProbeForRead` at `0x14019738a`
- `ntoskrnl!ProbeForRead` at `0x140197455`
- `ntoskrnl!ProbeForRead` at `0x140197544`
- `ntoskrnl!KeBugCheckEx` at `0x14019731a`
- `ntoskrnl!KeBugCheckEx` at `0x1401974eb`
- `ntoskrnl!KeBugCheckEx` at `0x14019731a`
- `ntoskrnl!KeBugCheckEx` at `0x1401974eb`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140197255`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1401977f0`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140197255`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1401977f0`
- `ntoskrnl!EtwActivityIdControl` at `0x14019780c`
- `ntoskrnl!EtwActivityIdControl` at `0x14019780c`

## pseudocode

```c
__int64 __fastcall xxxUserChangeDisplaySettings(
        _QWORD *a1,
        volatile void *a2,
        struct tagDESKTOP *a3,
        unsigned int a4,
        void *a5,
        enum _MODE a6,
        struct _DXGK_DISPLAY_SCENARIO_CONTEXT *a7)
{
  struct _UNICODE_STRING *v8; // rsi
  char *v9; // rdx
  __int64 v10; // r13
  SIZE_T v11; // r14
  SIZE_T v12; // r15
  volatile void *v13; // r12
  unsigned __int64 v14; // rcx
  unsigned int v15; // ebx
  struct tagTHREADINFO *BugCheckParameter4; // rax
  struct tagTHREADINFO *v17; // rax
  char *v18; // rdi
  size_t v19; // r15
  size_t v20; // r12
  struct tagTHREADINFO *v21; // rax
  struct tagTHREADINFO *v22; // rax
  unsigned int v24; // r15d
  char *v25; // rax
  char *v26; // rbx
  __int64 v27; // r12
  int v28; // ecx
  int v29; // eax
  unsigned int v30; // edx
  bool v31; // cf
  int v32; // edx
  __int64 v33; // rcx
  PWSTR Buffer; // rdx
  WCHAR *v35; // rax
  WCHAR v36; // r8
  WCHAR *v37; // rcx
  __int64 v38; // rsi
  __int64 v39; // r15
  int v40; // r9d
  int v41; // ecx
  int v42; // r9d
  char v43[4]; // [rsp+70h] [rbp-E8h] BYREF
  unsigned int v44; // [rsp+74h] [rbp-E4h] BYREF
  unsigned int v45; // [rsp+78h] [rbp-E0h] BYREF
  volatile void *v46; // [rsp+80h] [rbp-D8h] BYREF
  ULONG TimeIncrement; // [rsp+88h] [rbp-D0h] BYREF
  unsigned __int16 v48; // [rsp+8Ch] [rbp-CCh]
  __int16 v49; // [rsp+90h] [rbp-C8h]
  void *v50; // [rsp+98h] [rbp-C0h] BYREF
  volatile void *Address; // [rsp+A0h] [rbp-B8h] BYREF
  ULONG_PTR v52[2]; // [rsp+A8h] [rbp-B0h] BYREF
  __int64 (__fastcall *v53)(PVOID); // [rsp+B8h] [rbp-A0h]
  ULONG_PTR BugCheckParameter2[2]; // [rsp+C0h] [rbp-98h] BYREF
  __int64 (__fastcall *v55)(PVOID); // [rsp+D0h] [rbp-88h]
  int v56; // [rsp+D8h] [rbp-80h] BYREF
  __int64 v57; // [rsp+E0h] [rbp-78h] BYREF
  struct tagDESKTOP *v58; // [rsp+E8h] [rbp-70h] BYREF
  struct _DXGK_DISPLAY_SCENARIO_CONTEXT *v59[3]; // [rsp+F0h] [rbp-68h] BYREF
  GUID ActivityId; // [rsp+108h] [rbp-50h] BYREF

  v44 = a4;
  v58 = a3;
  Address = a1;
  v46 = a2;
  v50 = a5;
  v59[0] = a7;
  ActivityId = 0;
  v57 = MEMORY[0xFFFFF78000000320];
  TimeIncrement = KeQueryTimeIncrement();
  v8 = 0;
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(v52);
  if ( Address )
  {
    v10 = (unsigned int)((_DWORD)v9 + 16);
    v11 = (unsigned int)((_DWORD)v9 + 1);
    v59[1] = (struct _DXGK_DISPLAY_SCENARIO_CONTEXT *)v11;
    ProbeForRead(Address, v11, (_DWORD)v9 + 1);
    v12 = *(unsigned __int16 *)a1;
    v13 = (volatile void *)a1[1];
    v8 = (struct _UNICODE_STRING *)Win32AllocPoolWithQuotaZInitImpl(v14, v12 + 18, 0x73726447u);
    v15 = -1;
    if ( !v8 )
      goto LABEL_16;
    if ( v55 != (__int64 (__fastcall *)(PVOID))-1LL )
    {
      BugCheckParameter4 = PtiCurrent();
      KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, (ULONG_PTR)v8, (ULONG_PTR)BugCheckParameter4);
    }
    v17 = PtiCurrent();
    BugCheckParameter2[0] = *((_QWORD *)v17 + 47);
    *((_QWORD *)v17 + 47) = BugCheckParameter2;
    BugCheckParameter2[1] = (ULONG_PTR)v8;
    v55 = GreDeleteFastMutex;
    v8->Buffer = &v8[1].Length;
    v8->Length = v12;
    v8->MaximumLength = v12 + 2;
    v9 = 0;
    if ( (_WORD)v12 )
    {
      ProbeForRead(v13, v12, v11);
      memmove(v8->Buffer, (const void *)v13, v12);
      v9 = 0;
    }
    v8->Buffer[v12 >> 1] = 0;
  }
  else
  {
    v10 = 16;
    v11 = 1;
    v15 = -1;
  }
  v18 = v9;
  if ( v46 )
  {
    v48 = (unsigned __int16)v9;
    v49 = (__int16)v9;
    v59[2] = (struct _DXGK_DISPLAY_SCENARIO_CONTEXT *)v11;
    ProbeForRead(v46, v11, 4u);
    v48 = *((_WORD *)v46 + 34);
    v19 = v48;
    v20 = *((unsigned __int16 *)v46 + 35);
    v49 = *((_WORD *)v46 + 35);
    if ( (unsigned __int16)(v48 - 188) > 0x20u )
    {
      v15 = -2;
    }
    else
    {
      v18 = (char *)Win32AllocPoolWithQuotaZInitImpl(0xBCu, v20 + 220, 0x73726447u);
      if ( v18 )
      {
        if ( v53 != (__int64 (__fastcall *)(PVOID))-1LL )
        {
          v21 = PtiCurrent();
          KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)v52, (ULONG_PTR)v18, (ULONG_PTR)v21);
        }
        v22 = PtiCurrent();
        v52[0] = *((_QWORD *)v22 + 47);
        *((_QWORD *)v22 + 47) = v52;
        v52[1] = (ULONG_PTR)v18;
        v53 = GreDeleteFastMutex;
        ProbeForRead(v46, (unsigned int)(v19 + v20), 4u);
        memmove(v18, (const void *)v46, v19);
        memmove(v18 + 220, (char *)v46 + v19, v20);
        *((_WORD *)v18 + 34) = 220;
        *((_WORD *)v18 + 35) = v20;
        goto LABEL_17;
      }
    }
LABEL_16:
    Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(v52);
    Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
    return v15;
  }
LABEL_17:
  v24 = xxxUserChangeDisplaySettingsInternal(v8, (struct _devicemodeW *)v18, v58, v44, v50, a6, v59[0]);
  v45 = v24;
  v25 = (char *)Win32AllocPoolZInitImpl(0x100u, 0x90u, 0x64437355u);
  v26 = v25;
  if ( v25 )
  {
    v27 = v57 * TimeIncrement;
    *(_DWORD *)v25 = 4;
    *((_DWORD *)v25 + 1) = 144;
    *((_DWORD *)v25 + 10) = 0;
    *((_QWORD *)v25 + 4) = 0;
    *((_QWORD *)v25 + 1) = 0;
    *((_OWORD *)v25 + 1) = 0;
    *((_QWORD *)v25 + 7) = v27;
    if ( !v46 || (v28 = v11, !v18) )
      v28 = 0;
    *((_DWORD *)v25 + 35) = v28 | *((_DWORD *)v25 + 35) & 0xFFFFFFFE;
    if ( !Address || !v8 || !v8->Length || (v29 = 2, !v8->Buffer) )
      v29 = 0;
    v30 = (a6 == KernelMode ? 4 : 0) | v29 & 0xFFFFFFF3 | *((_DWORD *)v26 + 35) & 0xFFFFFFF1;
    v31 = v50 != 0;
    v50 = (void *)-(__int64)v50;
    v32 = (v31 ? 0 : 8) | v30;
    *((_DWORD *)v26 + 35) = v32;
    *((_DWORD *)v26 + 12) = v44;
    *((_DWORD *)v26 + 13) = v24;
    if ( (v32 & 2) != 0 )
    {
      v33 = 2147483646;
      Buffer = v8->Buffer;
      v35 = (WCHAR *)(v26 + 108);
      do
      {
        if ( !v33 )
          break;
        v36 = *Buffer;
        if ( !*Buffer )
          break;
        ++Buffer;
        *v35++ = v36;
        v33 -= v11;
        v10 -= v11;
      }
      while ( v10 );
      v37 = v35 - 1;
      if ( v10 )
        v37 = v35;
      *v37 = 0;
      if ( !v10 )
        *((_WORD *)v26 + 54) = 0;
    }
    if ( ((unsigned __int8)*((_DWORD *)v26 + 35) & (unsigned __int8)v11) != 0 && *((_WORD *)v18 + 34) >= 0xB4u )
    {
      *((_DWORD *)v26 + 16) = *((_DWORD *)v18 + 18);
      *(_QWORD *)(v26 + 68) = *(_QWORD *)(v18 + 76);
      *((_DWORD *)v26 + 19) = *((_DWORD *)v18 + 42);
      *((_DWORD *)v26 + 20) = *((_DWORD *)v18 + 43);
      *((_DWORD *)v26 + 21) = *((_DWORD *)v18 + 44);
      *((_DWORD *)v26 + 22) = *((_DWORD *)v18 + 46);
      *((_DWORD *)v26 + 23) = *((unsigned __int16 *)v18 + 35);
      *((_DWORD *)v26 + 24) = *((_DWORD *)v18 + 21);
      *((_DWORD *)v26 + 25) = *((_DWORD *)v18 + 22);
      *((_DWORD *)v26 + 26) = *((_DWORD *)v18 + 45);
    }
    DrvDxgkWriteDiagEntry(v26);
    v38 = MEMORY[0xFFFFF78000000320];
    v39 = KeQueryTimeIncrement();
    EtwActivityIdControl(3u, &ActivityId);
    if ( (unsigned int)dword_140293E08 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140293E08, 0x200000000004LL) )
    {
      v43[0] = a6;
      Address = (volatile void *)(v38 * v39);
      v50 = (void *)v27;
      v24 = v45;
      TimeIncrement = v45;
      v45 = v44;
      v44 = v46 == 0;
      v46 = v26 + 108;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>>(
        v44,
        (unsigned int)byte_14026F833,
        (unsigned int)&ActivityId,
        v40,
        (__int64)&v46,
        (__int64)&v44,
        (__int64)&v45,
        (__int64)&TimeIncrement,
        (__int64)&v50,
        (__int64)&Address,
        (__int64)v43);
    }
    else
    {
      v24 = v45;
    }
    if ( ((unsigned __int8)*((_DWORD *)v26 + 35) & (unsigned __int8)v11) != 0 && (unsigned int)dword_140293E08 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_140293E08, 0x200000000004LL) )
      {
        TimeIncrement = *((_DWORD *)v26 + 26);
        v45 = *((_DWORD *)v26 + 25);
        v44 = *((_DWORD *)v26 + 24);
        v56 = *((_DWORD *)v26 + 23);
        LODWORD(v57) = *((_DWORD *)v26 + 22);
        LODWORD(v58) = *((_DWORD *)v26 + 21);
        LODWORD(v59[0]) = *((_DWORD *)v26 + 20);
        LODWORD(v50) = *((_DWORD *)v26 + 18);
        LODWORD(Address) = *((_DWORD *)v26 + 17);
        LODWORD(v46) = *((_DWORD *)v26 + 16);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v41,
          (unsigned int)&word_14026F7A6,
          (unsigned int)&ActivityId,
          v42,
          (__int64)&v46,
          (__int64)&Address,
          (__int64)&v50,
          (__int64)v59,
          (__int64)&v58,
          (__int64)&v57,
          (__int64)&v56,
          (__int64)&v44,
          (__int64)&v45,
          (__int64)&TimeIncrement);
      }
    }
    GreDeleteFastMutex(v26);
  }
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(v52);
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  return v24;
}

```

## disassembly

```asm
0x1401971d0  push    rbx
0x1401971d2  push    rsi
0x1401971d3  push    rdi
0x1401971d4  push    r12
0x1401971d6  push    r13
0x1401971d8  push    r14
0x1401971da  push    r15
0x1401971dc  sub     rsp, 120h
0x1401971e3  mov     rax, cs:__security_cookie
0x1401971ea  xor     rax, rsp
0x1401971ed  mov     [rsp+158h+var_40], rax
0x1401971f5  mov     [rsp+158h+var_E4], r9d
0x1401971fa  mov     [rsp+158h+var_70], r8
0x140197202  mov     rbx, rcx
0x140197205  mov     [rsp+158h+Address], rcx
0x14019720d  mov     [rsp+158h+var_D8], rdx
0x140197215  mov     rax, [rsp+158h+arg_20]
0x14019721d  mov     [rsp+158h+var_C0], rax
0x140197225  mov     rax, [rsp+158h+arg_30]
0x14019722d  mov     [rsp+158h+var_68], rax
0x140197235  xorps   xmm0, xmm0
0x140197238  movups  xmmword ptr [rsp+158h+ActivityId.Data1], xmm0
0x140197240  mov     rax, 0FFFFF78000000320h
0x14019724a  mov     rax, [rax]
0x14019724d  mov     [rsp+158h+var_78], rax
0x140197255  call    cs:__imp_KeQueryTimeIncrement
0x14019725c  nop     dword ptr [rax+rax+00h]
0x140197261  mov     [rsp+158h+var_D0], eax
0x140197268  xor     edx, edx
0x14019726a  mov     esi, edx
0x14019726c  lea     rcx, [rsp+158h+BugCheckParameter2]
0x140197274  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x140197279  lea     rcx, [rsp+158h+var_B0]
0x140197281  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x140197286  mov     rcx, [rsp+158h+Address]
0x14019728e  test    rcx, rcx
0x140197291  jz      loc_1401973FE
0x140197297  lea     r13d, [rdx+10h]
0x14019729b  mov     [rsp+158h+var_60], r13
0x1401972a3  mov     rcx, [rsp+158h+Address]; Address
0x1401972ab  lea     r14d, [rdx+1]
0x1401972af  mov     [rsp+158h+var_60], r14
0x1401972b7  mov     r8d, r14d; Alignment
0x1401972ba  mov     edx, r14d; Length
0x1401972bd  call    cs:__imp_ProbeForRead
0x1401972c4  nop     dword ptr [rax+rax+00h]
0x1401972c9  movzx   r15d, word ptr [rbx]
0x1401972cd  mov     r12, [rbx+8]
0x1401972d1  mov     rdi, r15
0x1401972d4  lea     rdx, [r15+12h]; unsigned __int64
0x1401972d8  mov     r8d, 73726447h; unsigned int
0x1401972de  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401972e3  mov     rsi, rax
0x1401972e6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1401972ea  test    rax, rax
0x1401972ed  jz      loc_1401975B6
0x1401972f3  cmp     [rsp+158h+var_88], rbx
0x1401972fb  jz      short loc_140197327
0x1401972fd  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140197302  mov     [rsp+158h+BugCheckParameter4], rax; BugCheckParameter4
0x140197307  mov     r9, rsi; BugCheckParameter3
0x14019730a  lea     r8, [rsp+158h+BugCheckParameter2]; BugCheckParameter2
0x140197312  lea     edx, [rbx+13h]; BugCheckParameter1
0x140197315  mov     ecx, 164h; BugCheckCode
0x14019731a  call    cs:__imp_KeBugCheckEx
0x140197327  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14019732c  mov     rcx, [rax+178h]
0x140197333  mov     [rsp+158h+BugCheckParameter2], rcx
0x14019733b  lea     rcx, [rsp+158h+BugCheckParameter2]
0x140197343  mov     [rax+178h], rcx
0x14019734a  mov     [rsp+158h+var_90], rsi
0x140197352  lea     rdx, GreDeleteFastMutex
0x140197359  mov     [rsp+158h+var_88], rdx
0x140197361  lea     rax, [rsi+10h]
0x140197365  mov     [rsi+8], rax
0x140197369  mov     [rsi], r15w
0x14019736d  mov     eax, 2
0x140197372  add     eax, r15d
0x140197375  mov     [rsi+2], ax
0x140197379  xor     edx, edx
0x14019737b  test    r15w, r15w
0x14019737f  jz      short loc_1401973CD
0x140197381  mov     r8d, r14d; Alignment
0x140197384  mov     rdx, rdi; Length
0x140197387  mov     rcx, r12; Address
0x14019738a  call    cs:__imp_ProbeForRead
0x140197391  nop     dword ptr [rax+rax+00h]
0x140197396  mov     r8, rdi; Size
0x140197399  mov     rdx, r12; Src
0x14019739c  mov     rcx, [rsi+8]; void *
0x1401973a0  call    memmove
0x1401973a5  xor     edx, edx
0x1401973a7  jmp     short loc_1401973CD
0x1401973a9  lea     rcx, [rsp+158h+var_B0]
0x1401973b1  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401973b6  lea     rcx, [rsp+158h+BugCheckParameter2]
0x1401973be  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401973c3  mov     eax, 0FFFFFFFBh
0x1401973c8  jmp     loc_140197A55
0x1401973cd  shr     rdi, 1
0x1401973d0  mov     rcx, [rsi+8]
0x1401973d4  mov     [rcx+rdi*2], dx
0x1401973d8  jmp     short loc_14019740C
0x1401973da  lea     rcx, [rsp+158h+var_B0]
0x1401973e2  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401973e7  lea     rcx, [rsp+158h+BugCheckParameter2]
0x1401973ef  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401973f4  mov     eax, 0FFFFFFFBh
0x1401973f9  jmp     loc_140197A55
0x1401973fe  mov     r13d, 10h
0x140197404  lea     r14d, [r13-0Fh]
0x140197408  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14019740c  mov     rdi, rdx
0x14019740f  mov     rax, [rsp+158h+var_D8]
0x140197417  test    rax, rax
0x14019741a  jz      loc_1401975FB
0x140197420  mov     [rsp+158h+var_CC], dx
0x140197428  mov     [rsp+158h+var_C8], dx
0x140197430  mov     [rsp+158h+var_58], 48h ; 'H'
0x14019743c  mov     rcx, [rsp+158h+var_D8]; Address
0x140197444  mov     [rsp+158h+var_58], r14
0x14019744c  mov     r8d, 4; Alignment
0x140197452  mov     rdx, r14; Length
0x140197455  call    cs:__imp_ProbeForRead
0x14019745c  nop     dword ptr [rax+rax+00h]
0x140197461  mov     rax, [rsp+158h+var_D8]
0x140197469  movzx   r15d, word ptr [rax+44h]
0x14019746e  mov     [rsp+158h+var_CC], r15w
0x140197477  mov     rax, [rsp+158h+var_D8]
0x14019747f  movzx   r12d, word ptr [rax+46h]
0x140197484  mov     [rsp+158h+var_C8], r12w
0x14019748d  mov     ecx, 0BCh; unsigned __int64
0x140197492  movzx   eax, r15w
0x140197496  sub     ax, cx
0x140197499  cmp     ax, 20h ; ' '
0x14019749d  ja      loc_1401975B1
0x1401974a3  lea     rdx, [r12+0DCh]; unsigned __int64
0x1401974ab  mov     r8d, 73726447h; unsigned int
0x1401974b1  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401974b6  mov     rdi, rax
0x1401974b9  test    rax, rax
0x1401974bc  jz      loc_1401975B6
0x1401974c2  cmp     [rsp+158h+var_A0], rbx
0x1401974ca  jz      short loc_1401974F8
0x1401974cc  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401974d1  mov     [rsp+158h+BugCheckParameter4], rax; BugCheckParameter4
0x1401974d6  mov     r9, rdi; BugCheckParameter3
0x1401974d9  lea     r8, [rsp+158h+var_B0]; BugCheckParameter2
0x1401974e1  mov     edx, 12h; BugCheckParameter1
0x1401974e6  mov     ecx, 164h; BugCheckCode
0x1401974eb  call    cs:__imp_KeBugCheckEx
0x1401974f8  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401974fd  mov     rcx, [rax+178h]
0x140197504  mov     [rsp+158h+var_B0], rcx
0x14019750c  lea     rcx, [rsp+158h+var_B0]
0x140197514  mov     [rax+178h], rcx
0x14019751b  mov     [rsp+158h+var_A8], rdi
0x140197523  lea     rax, GreDeleteFastMutex
0x14019752a  mov     [rsp+158h+var_A0], rax
0x140197532  lea     edx, [r15+r12]; Length
0x140197536  mov     r8d, 4; Alignment
0x14019753c  mov     rcx, [rsp+158h+var_D8]; Address
0x140197544  call    cs:__imp_ProbeForRead
0x14019754b  nop     dword ptr [rax+rax+00h]
0x140197550  mov     rdx, [rsp+158h+var_D8]; Src
0x140197558  mov     r8, r15; Size
0x14019755b  mov     rcx, rdi; void *
0x14019755e  call    memmove
0x140197563  mov     rdx, [rsp+158h+var_D8]
0x14019756b  add     rdx, r15; Src
0x14019756e  lea     rcx, [rdi+0DCh]; void *
0x140197575  mov     r8, r12; Size
0x140197578  call    memmove
0x14019757d  mov     eax, 0DCh
0x140197582  mov     [rdi+44h], ax
0x140197586  mov     [rdi+46h], r12w
0x14019758b  jmp     short loc_1401975FB
0x14019758d  lea     rcx, [rsp+158h+var_B0]
0x140197595  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x14019759a  lea     rcx, [rsp+158h+BugCheckParameter2]
0x1401975a2  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401975a7  mov     eax, 0FFFFFFFEh
0x1401975ac  jmp     loc_140197A55
0x1401975b1  mov     ebx, 0FFFFFFFEh
0x1401975b6  lea     rcx, [rsp+158h+var_B0]
0x1401975be  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401975c3  lea     rcx, [rsp+158h+BugCheckParameter2]
0x1401975cb  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401975d0  mov     eax, ebx
0x1401975d2  jmp     loc_140197A55
0x1401975d7  lea     rcx, [rsp+158h+var_B0]
0x1401975df  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401975e4  lea     rcx, [rsp+158h+BugCheckParameter2]
0x1401975ec  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401975f1  mov     eax, 0FFFFFFFEh
0x1401975f6  jmp     loc_140197A55
0x1401975fb  mov     rax, [rsp+158h+var_68]
0x140197603  mov     [rsp+158h+var_128], rax; struct _DXGK_DISPLAY_SCENARIO_CONTEXT *
0x140197608  mov     eax, [rsp+158h+arg_28]
0x14019760f  mov     [rsp+158h+var_130], eax; enum _MODE
0x140197613  mov     rax, [rsp+158h+var_C0]
0x14019761b  mov     [rsp+158h+BugCheckParameter4], rax; void *
0x140197620  mov     r9d, [rsp+158h+var_E4]; unsigned int
0x140197625  mov     r8, [rsp+158h+var_70]; struct tagDESKTOP *
0x14019762d  mov     rdx, rdi; struct _devicemodeW *
0x140197630  mov     rcx, rsi; struct _UNICODE_STRING *
0x140197633  call    ?xxxUserChangeDisplaySettingsInternal@@YAJPEAU_UNICODE_STRING@@PEAU_devicemodeW@@PEAUtagDESKTOP@@KPEAXW4_MODE@@PEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z; xxxUserChangeDisplaySettingsInternal(_UNICODE_STRING *,_devicemodeW *,tagDESKTOP *,ulong,void *,_MODE,_DXGK_DISPLAY_SCENARIO_CONTEXT *)
0x140197638  mov     r15d, eax
0x14019763b  mov     [rsp+158h+var_E0], eax
0x14019763f  mov     edx, 90h; unsigned __int64
0x140197644  lea     ecx, [rdx+70h]; unsigned __int64
0x140197647  mov     r8d, 64437355h; unsigned int
0x14019764d  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x140197652  mov     rbx, rax
0x140197655  xor     r10d, r10d
0x140197658  test    rax, rax
0x14019765b  jz      loc_140197A38
0x140197661  mov     r12d, [rsp+158h+var_D0]
0x140197669  imul    r12, [rsp+158h+var_78]
0x140197672  mov     dword ptr [rax], 4
0x140197678  mov     dword ptr [rax+4], 90h
0x14019767f  mov     [rax+28h], r10d
0x140197683  mov     [rax+20h], r10
0x140197687  xor     eax, eax
0x140197689  mov     [rbx+8], rax
0x14019768d  xorps   xmm0, xmm0
0x140197690  movups  xmmword ptr [rbx+10h], xmm0
0x140197694  mov     [rbx+38h], r12
0x140197698  mov     rax, [rsp+158h+var_D8]
0x1401976a0  test    rax, rax
0x1401976a3  jz      short loc_1401976AD
0x1401976a5  test    rdi, rdi
0x1401976a8  mov     ecx, r14d
0x1401976ab  jnz     short loc_1401976B0
0x1401976ad  mov     ecx, r10d
0x1401976b0  mov     eax, [rbx+8Ch]
0x1401976b6  and     eax, 0FFFFFFFEh
0x1401976b9  or      eax, ecx
0x1401976bb  mov     [rbx+8Ch], eax
0x1401976c1  mov     rax, [rsp+158h+Address]
0x1401976c9  test    rax, rax
0x1401976cc  jz      short loc_1401976E4
0x1401976ce  test    rsi, rsi
0x1401976d1  jz      short loc_1401976E4
0x1401976d3  cmp     [rsi], r10w
0x1401976d7  jbe     short loc_1401976E4
0x1401976d9  cmp     [rsi+8], r10
0x1401976dd  mov     eax, 2
0x1401976e2  jnz     short loc_1401976E7
0x1401976e4  mov     eax, r10d
0x1401976e7  mov     edx, [rbx+8Ch]
0x1401976ed  and     edx, 0FFFFFFFDh
0x1401976f0  or      edx, eax
0x1401976f2  and     edx, 0FFFFFFFBh
0x1401976f5  mov     eax, [rsp+158h+arg_28]
0x1401976fc  neg     eax
0x1401976fe  sbb     ecx, ecx
0x140197700  not     ecx
0x140197702  and     ecx, 4
0x140197705  or      edx, ecx
0x140197707  and     edx, 0FFFFFFF7h
0x14019770a  neg     [rsp+158h+var_C0]
0x140197712  sbb     eax, eax
0x140197714  not     eax
0x140197716  and     eax, 8
0x140197719  or      edx, eax
0x14019771b  mov     [rbx+8Ch], edx
0x140197721  mov     eax, [rsp+158h+var_E4]
0x140197725  mov     [rbx+30h], eax
0x140197728  mov     [rbx+34h], r15d
0x14019772c  test    dl, 2
0x14019772f  jz      short loc_140197777
0x140197731  mov     ecx, 7FFFFFFEh
0x140197736  mov     rdx, [rsi+8]
0x14019773a  lea     rax, [rbx+6Ch]
0x14019773e  test    rcx, rcx
0x140197741  jz      short loc_140197761
0x140197743  movzx   r8d, word ptr [rdx]
0x140197747  test    r8w, r8w
0x14019774b  jz      short loc_140197761
0x14019774d  add     rdx, 2
0x140197751  mov     [rax], r8w
0x140197755  add     rax, 2
0x140197759  sub     rcx, r14
0x14019775c  sub     r13, r14
0x14019775f  jnz     short loc_14019773E
0x140197761  lea     rcx, [rax-2]
0x140197765  test    r13, r13
0x140197768  cmovnz  rcx, rax
0x14019776c  mov     [rcx], r10w
0x140197770  jnz     short loc_140197777
0x140197772  mov     [rbx+6Ch], r10w
0x140197777  mov     eax, [rbx+8Ch]
0x14019777d  test    r14b, al
0x140197780  jz      short loc_1401977DB
0x140197782  mov     eax, 0B4h
0x140197787  cmp     [rdi+44h], ax
0x14019778b  jb      short loc_1401977DB
0x14019778d  mov     eax, [rdi+48h]
0x140197790  mov     [rbx+40h], eax
  ... truncated ...
```
