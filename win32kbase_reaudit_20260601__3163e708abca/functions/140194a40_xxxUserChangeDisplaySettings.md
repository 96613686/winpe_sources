# xxxUserChangeDisplaySettings

- ea: `0x140194a40`
- end: `0x1401952e9`
- name: `xxxUserChangeDisplaySettings`
- size: `2217`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task`

## callers

- `0x1401d9050`

## callees

- `0x140003e34`
- `0x140004030`
- `0x14002ab14`
- `0x1400411c0`
- `0x140043810`
- `0x1400449b0`
- `0x1400757c8`
- `0x1400759e0`
- `0x14016d200`
- `0x1401940e0`
- `0x140194a40`
- `0x1401be850`
- `0x140238b10`
- `0x140239180`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140194b2d`
- `ntoskrnl!ProbeForRead` at `0x140194bfa`
- `ntoskrnl!ProbeForRead` at `0x140194cc5`
- `ntoskrnl!ProbeForRead` at `0x140194db4`
- `ntoskrnl!ProbeForRead` at `0x140194b2d`
- `ntoskrnl!ProbeForRead` at `0x140194bfa`
- `ntoskrnl!ProbeForRead` at `0x140194cc5`
- `ntoskrnl!ProbeForRead` at `0x140194db4`
- `ntoskrnl!KeBugCheckEx` at `0x140194b8a`
- `ntoskrnl!KeBugCheckEx` at `0x140194d5b`
- `ntoskrnl!KeBugCheckEx` at `0x140194b8a`
- `ntoskrnl!KeBugCheckEx` at `0x140194d5b`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140194ac5`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140195060`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140194ac5`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140195060`
- `ntoskrnl!EtwActivityIdControl` at `0x14019507c`
- `ntoskrnl!EtwActivityIdControl` at `0x14019507c`

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
    if ( (unsigned int)dword_140294E08 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140294E08, 0x200000000004LL) )
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
        (unsigned int)byte_14026FAB3,
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
    if ( ((unsigned __int8)*((_DWORD *)v26 + 35) & (unsigned __int8)v11) != 0 && (unsigned int)dword_140294E08 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_140294E08, 0x200000000004LL) )
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
          (unsigned int)&word_14026FA26,
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
0x140194a40  push    rbx
0x140194a42  push    rsi
0x140194a43  push    rdi
0x140194a44  push    r12
0x140194a46  push    r13
0x140194a48  push    r14
0x140194a4a  push    r15
0x140194a4c  sub     rsp, 120h
0x140194a53  mov     rax, cs:__security_cookie
0x140194a5a  xor     rax, rsp
0x140194a5d  mov     [rsp+158h+var_40], rax
0x140194a65  mov     [rsp+158h+var_E4], r9d
0x140194a6a  mov     [rsp+158h+var_70], r8
0x140194a72  mov     rbx, rcx
0x140194a75  mov     [rsp+158h+Address], rcx
0x140194a7d  mov     [rsp+158h+var_D8], rdx
0x140194a85  mov     rax, [rsp+158h+arg_20]
0x140194a8d  mov     [rsp+158h+var_C0], rax
0x140194a95  mov     rax, [rsp+158h+arg_30]
0x140194a9d  mov     [rsp+158h+var_68], rax
0x140194aa5  xorps   xmm0, xmm0
0x140194aa8  movups  xmmword ptr [rsp+158h+ActivityId.Data1], xmm0
0x140194ab0  mov     rax, 0FFFFF78000000320h
0x140194aba  mov     rax, [rax]
0x140194abd  mov     [rsp+158h+var_78], rax
0x140194ac5  call    cs:__imp_KeQueryTimeIncrement
0x140194acc  nop     dword ptr [rax+rax+00h]
0x140194ad1  mov     [rsp+158h+var_D0], eax
0x140194ad8  xor     edx, edx
0x140194ada  mov     esi, edx
0x140194adc  lea     rcx, [rsp+158h+BugCheckParameter2]
0x140194ae4  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194ae9  lea     rcx, [rsp+158h+var_B0]
0x140194af1  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194af6  mov     rcx, [rsp+158h+Address]
0x140194afe  test    rcx, rcx
0x140194b01  jz      loc_140194C6E
0x140194b07  lea     r13d, [rdx+10h]
0x140194b0b  mov     [rsp+158h+var_60], r13
0x140194b13  mov     rcx, [rsp+158h+Address]; Address
0x140194b1b  lea     r14d, [rdx+1]
0x140194b1f  mov     [rsp+158h+var_60], r14
0x140194b27  mov     r8d, r14d; Alignment
0x140194b2a  mov     edx, r14d; Length
0x140194b2d  call    cs:__imp_ProbeForRead
0x140194b34  nop     dword ptr [rax+rax+00h]
0x140194b39  movzx   r15d, word ptr [rbx]
0x140194b3d  mov     r12, [rbx+8]
0x140194b41  mov     rdi, r15
0x140194b44  lea     rdx, [r15+12h]; unsigned __int64
0x140194b48  mov     r8d, 73726447h; unsigned int
0x140194b4e  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x140194b53  mov     rsi, rax
0x140194b56  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140194b5a  test    rax, rax
0x140194b5d  jz      loc_140194E26
0x140194b63  cmp     [rsp+158h+var_88], rbx
0x140194b6b  jz      short loc_140194B97
0x140194b6d  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140194b72  mov     [rsp+158h+BugCheckParameter4], rax; BugCheckParameter4
0x140194b77  mov     r9, rsi; BugCheckParameter3
0x140194b7a  lea     r8, [rsp+158h+BugCheckParameter2]; BugCheckParameter2
0x140194b82  lea     edx, [rbx+13h]; BugCheckParameter1
0x140194b85  mov     ecx, 164h; BugCheckCode
0x140194b8a  call    cs:__imp_KeBugCheckEx
0x140194b97  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140194b9c  mov     rcx, [rax+178h]
0x140194ba3  mov     [rsp+158h+BugCheckParameter2], rcx
0x140194bab  lea     rcx, [rsp+158h+BugCheckParameter2]
0x140194bb3  mov     [rax+178h], rcx
0x140194bba  mov     [rsp+158h+var_90], rsi
0x140194bc2  lea     rdx, GreDeleteFastMutex
0x140194bc9  mov     [rsp+158h+var_88], rdx
0x140194bd1  lea     rax, [rsi+10h]
0x140194bd5  mov     [rsi+8], rax
0x140194bd9  mov     [rsi], r15w
0x140194bdd  mov     eax, 2
0x140194be2  add     eax, r15d
0x140194be5  mov     [rsi+2], ax
0x140194be9  xor     edx, edx
0x140194beb  test    r15w, r15w
0x140194bef  jz      short loc_140194C3D
0x140194bf1  mov     r8d, r14d; Alignment
0x140194bf4  mov     rdx, rdi; Length
0x140194bf7  mov     rcx, r12; Address
0x140194bfa  call    cs:__imp_ProbeForRead
0x140194c01  nop     dword ptr [rax+rax+00h]
0x140194c06  mov     r8, rdi; Size
0x140194c09  mov     rdx, r12; Src
0x140194c0c  mov     rcx, [rsi+8]; void *
0x140194c10  call    memmove
0x140194c15  xor     edx, edx
0x140194c17  jmp     short loc_140194C3D
0x140194c19  lea     rcx, [rsp+158h+var_B0]
0x140194c21  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194c26  lea     rcx, [rsp+158h+BugCheckParameter2]
0x140194c2e  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194c33  mov     eax, 0FFFFFFFBh
0x140194c38  jmp     loc_1401952C5
0x140194c3d  shr     rdi, 1
0x140194c40  mov     rcx, [rsi+8]
0x140194c44  mov     [rcx+rdi*2], dx
0x140194c48  jmp     short loc_140194C7C
0x140194c4a  lea     rcx, [rsp+158h+var_B0]
0x140194c52  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194c57  lea     rcx, [rsp+158h+BugCheckParameter2]
0x140194c5f  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194c64  mov     eax, 0FFFFFFFBh
0x140194c69  jmp     loc_1401952C5
0x140194c6e  mov     r13d, 10h
0x140194c74  lea     r14d, [r13-0Fh]
0x140194c78  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140194c7c  mov     rdi, rdx
0x140194c7f  mov     rax, [rsp+158h+var_D8]
0x140194c87  test    rax, rax
0x140194c8a  jz      loc_140194E6B
0x140194c90  mov     [rsp+158h+var_CC], dx
0x140194c98  mov     [rsp+158h+var_C8], dx
0x140194ca0  mov     [rsp+158h+var_58], 48h ; 'H'
0x140194cac  mov     rcx, [rsp+158h+var_D8]; Address
0x140194cb4  mov     [rsp+158h+var_58], r14
0x140194cbc  mov     r8d, 4; Alignment
0x140194cc2  mov     rdx, r14; Length
0x140194cc5  call    cs:__imp_ProbeForRead
0x140194ccc  nop     dword ptr [rax+rax+00h]
0x140194cd1  mov     rax, [rsp+158h+var_D8]
0x140194cd9  movzx   r15d, word ptr [rax+44h]
0x140194cde  mov     [rsp+158h+var_CC], r15w
0x140194ce7  mov     rax, [rsp+158h+var_D8]
0x140194cef  movzx   r12d, word ptr [rax+46h]
0x140194cf4  mov     [rsp+158h+var_C8], r12w
0x140194cfd  mov     ecx, 0BCh; unsigned __int64
0x140194d02  movzx   eax, r15w
0x140194d06  sub     ax, cx
0x140194d09  cmp     ax, 20h ; ' '
0x140194d0d  ja      loc_140194E21
0x140194d13  lea     rdx, [r12+0DCh]; unsigned __int64
0x140194d1b  mov     r8d, 73726447h; unsigned int
0x140194d21  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x140194d26  mov     rdi, rax
0x140194d29  test    rax, rax
0x140194d2c  jz      loc_140194E26
0x140194d32  cmp     [rsp+158h+var_A0], rbx
0x140194d3a  jz      short loc_140194D68
0x140194d3c  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140194d41  mov     [rsp+158h+BugCheckParameter4], rax; BugCheckParameter4
0x140194d46  mov     r9, rdi; BugCheckParameter3
0x140194d49  lea     r8, [rsp+158h+var_B0]; BugCheckParameter2
0x140194d51  mov     edx, 12h; BugCheckParameter1
0x140194d56  mov     ecx, 164h; BugCheckCode
0x140194d5b  call    cs:__imp_KeBugCheckEx
0x140194d68  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140194d6d  mov     rcx, [rax+178h]
0x140194d74  mov     [rsp+158h+var_B0], rcx
0x140194d7c  lea     rcx, [rsp+158h+var_B0]
0x140194d84  mov     [rax+178h], rcx
0x140194d8b  mov     [rsp+158h+var_A8], rdi
0x140194d93  lea     rax, GreDeleteFastMutex
0x140194d9a  mov     [rsp+158h+var_A0], rax
0x140194da2  lea     edx, [r15+r12]; Length
0x140194da6  mov     r8d, 4; Alignment
0x140194dac  mov     rcx, [rsp+158h+var_D8]; Address
0x140194db4  call    cs:__imp_ProbeForRead
0x140194dbb  nop     dword ptr [rax+rax+00h]
0x140194dc0  mov     rdx, [rsp+158h+var_D8]; Src
0x140194dc8  mov     r8, r15; Size
0x140194dcb  mov     rcx, rdi; void *
0x140194dce  call    memmove
0x140194dd3  mov     rdx, [rsp+158h+var_D8]
0x140194ddb  add     rdx, r15; Src
0x140194dde  lea     rcx, [rdi+0DCh]; void *
0x140194de5  mov     r8, r12; Size
0x140194de8  call    memmove
0x140194ded  mov     eax, 0DCh
0x140194df2  mov     [rdi+44h], ax
0x140194df6  mov     [rdi+46h], r12w
0x140194dfb  jmp     short loc_140194E6B
0x140194dfd  lea     rcx, [rsp+158h+var_B0]
0x140194e05  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194e0a  lea     rcx, [rsp+158h+BugCheckParameter2]
0x140194e12  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194e17  mov     eax, 0FFFFFFFEh
0x140194e1c  jmp     loc_1401952C5
0x140194e21  mov     ebx, 0FFFFFFFEh
0x140194e26  lea     rcx, [rsp+158h+var_B0]
0x140194e2e  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194e33  lea     rcx, [rsp+158h+BugCheckParameter2]
0x140194e3b  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194e40  mov     eax, ebx
0x140194e42  jmp     loc_1401952C5
0x140194e47  lea     rcx, [rsp+158h+var_B0]
0x140194e4f  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194e54  lea     rcx, [rsp+158h+BugCheckParameter2]
0x140194e5c  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194e61  mov     eax, 0FFFFFFFEh
0x140194e66  jmp     loc_1401952C5
0x140194e6b  mov     rax, [rsp+158h+var_68]
0x140194e73  mov     [rsp+158h+var_128], rax; struct _DXGK_DISPLAY_SCENARIO_CONTEXT *
0x140194e78  mov     eax, [rsp+158h+arg_28]
0x140194e7f  mov     [rsp+158h+var_130], eax; enum _MODE
0x140194e83  mov     rax, [rsp+158h+var_C0]
0x140194e8b  mov     [rsp+158h+BugCheckParameter4], rax; void *
0x140194e90  mov     r9d, [rsp+158h+var_E4]; unsigned int
0x140194e95  mov     r8, [rsp+158h+var_70]; struct tagDESKTOP *
0x140194e9d  mov     rdx, rdi; struct _devicemodeW *
0x140194ea0  mov     rcx, rsi; struct _UNICODE_STRING *
0x140194ea3  call    ?xxxUserChangeDisplaySettingsInternal@@YAJPEAU_UNICODE_STRING@@PEAU_devicemodeW@@PEAUtagDESKTOP@@KPEAXW4_MODE@@PEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z; xxxUserChangeDisplaySettingsInternal(_UNICODE_STRING *,_devicemodeW *,tagDESKTOP *,ulong,void *,_MODE,_DXGK_DISPLAY_SCENARIO_CONTEXT *)
0x140194ea8  mov     r15d, eax
0x140194eab  mov     [rsp+158h+var_E0], eax
0x140194eaf  mov     edx, 90h; unsigned __int64
0x140194eb4  lea     ecx, [rdx+70h]; unsigned __int64
0x140194eb7  mov     r8d, 64437355h; unsigned int
0x140194ebd  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x140194ec2  mov     rbx, rax
0x140194ec5  xor     r10d, r10d
0x140194ec8  test    rax, rax
0x140194ecb  jz      loc_1401952A8
0x140194ed1  mov     r12d, [rsp+158h+var_D0]
0x140194ed9  imul    r12, [rsp+158h+var_78]
0x140194ee2  mov     dword ptr [rax], 4
0x140194ee8  mov     dword ptr [rax+4], 90h
0x140194eef  mov     [rax+28h], r10d
0x140194ef3  mov     [rax+20h], r10
0x140194ef7  xor     eax, eax
0x140194ef9  mov     [rbx+8], rax
0x140194efd  xorps   xmm0, xmm0
0x140194f00  movups  xmmword ptr [rbx+10h], xmm0
0x140194f04  mov     [rbx+38h], r12
0x140194f08  mov     rax, [rsp+158h+var_D8]
0x140194f10  test    rax, rax
0x140194f13  jz      short loc_140194F1D
0x140194f15  test    rdi, rdi
0x140194f18  mov     ecx, r14d
0x140194f1b  jnz     short loc_140194F20
0x140194f1d  mov     ecx, r10d
0x140194f20  mov     eax, [rbx+8Ch]
0x140194f26  and     eax, 0FFFFFFFEh
0x140194f29  or      eax, ecx
0x140194f2b  mov     [rbx+8Ch], eax
0x140194f31  mov     rax, [rsp+158h+Address]
0x140194f39  test    rax, rax
0x140194f3c  jz      short loc_140194F54
0x140194f3e  test    rsi, rsi
0x140194f41  jz      short loc_140194F54
0x140194f43  cmp     [rsi], r10w
0x140194f47  jbe     short loc_140194F54
0x140194f49  cmp     [rsi+8], r10
0x140194f4d  mov     eax, 2
0x140194f52  jnz     short loc_140194F57
0x140194f54  mov     eax, r10d
0x140194f57  mov     edx, [rbx+8Ch]
0x140194f5d  and     edx, 0FFFFFFFDh
0x140194f60  or      edx, eax
0x140194f62  and     edx, 0FFFFFFFBh
0x140194f65  mov     eax, [rsp+158h+arg_28]
0x140194f6c  neg     eax
0x140194f6e  sbb     ecx, ecx
0x140194f70  not     ecx
0x140194f72  and     ecx, 4
0x140194f75  or      edx, ecx
0x140194f77  and     edx, 0FFFFFFF7h
0x140194f7a  neg     [rsp+158h+var_C0]
0x140194f82  sbb     eax, eax
0x140194f84  not     eax
0x140194f86  and     eax, 8
0x140194f89  or      edx, eax
0x140194f8b  mov     [rbx+8Ch], edx
0x140194f91  mov     eax, [rsp+158h+var_E4]
0x140194f95  mov     [rbx+30h], eax
0x140194f98  mov     [rbx+34h], r15d
0x140194f9c  test    dl, 2
0x140194f9f  jz      short loc_140194FE7
0x140194fa1  mov     ecx, 7FFFFFFEh
0x140194fa6  mov     rdx, [rsi+8]
0x140194faa  lea     rax, [rbx+6Ch]
0x140194fae  test    rcx, rcx
0x140194fb1  jz      short loc_140194FD1
0x140194fb3  movzx   r8d, word ptr [rdx]
0x140194fb7  test    r8w, r8w
0x140194fbb  jz      short loc_140194FD1
0x140194fbd  add     rdx, 2
0x140194fc1  mov     [rax], r8w
0x140194fc5  add     rax, 2
0x140194fc9  sub     rcx, r14
0x140194fcc  sub     r13, r14
0x140194fcf  jnz     short loc_140194FAE
0x140194fd1  lea     rcx, [rax-2]
0x140194fd5  test    r13, r13
0x140194fd8  cmovnz  rcx, rax
0x140194fdc  mov     [rcx], r10w
0x140194fe0  jnz     short loc_140194FE7
0x140194fe2  mov     [rbx+6Ch], r10w
0x140194fe7  mov     eax, [rbx+8Ch]
0x140194fed  test    r14b, al
0x140194ff0  jz      short loc_14019504B
0x140194ff2  mov     eax, 0B4h
0x140194ff7  cmp     [rdi+44h], ax
0x140194ffb  jb      short loc_14019504B
0x140194ffd  mov     eax, [rdi+48h]
0x140195000  mov     [rbx+40h], eax
  ... truncated ...
```
