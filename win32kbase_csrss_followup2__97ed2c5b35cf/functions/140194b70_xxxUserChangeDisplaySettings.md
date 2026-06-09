# xxxUserChangeDisplaySettings

- ea: `0x140194b70`
- end: `0x140195419`
- name: `xxxUserChangeDisplaySettings`
- size: `2217`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task`

## callers

- `0x1401d8af0`

## callees

- `0x140003e34`
- `0x140004030`
- `0x140033d94`
- `0x14004a0d0`
- `0x14004c720`
- `0x14004d770`
- `0x140076968`
- `0x140076b80`
- `0x14016d9a0`
- `0x140194210`
- `0x140194b70`
- `0x1401be2f0`
- `0x140238160`
- `0x140238800`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140194c5d`
- `ntoskrnl!ProbeForRead` at `0x140194d2a`
- `ntoskrnl!ProbeForRead` at `0x140194df5`
- `ntoskrnl!ProbeForRead` at `0x140194ee4`
- `ntoskrnl!ProbeForRead` at `0x140194c5d`
- `ntoskrnl!ProbeForRead` at `0x140194d2a`
- `ntoskrnl!ProbeForRead` at `0x140194df5`
- `ntoskrnl!ProbeForRead` at `0x140194ee4`
- `ntoskrnl!KeBugCheckEx` at `0x140194cba`
- `ntoskrnl!KeBugCheckEx` at `0x140194e8b`
- `ntoskrnl!KeBugCheckEx` at `0x140194cba`
- `ntoskrnl!KeBugCheckEx` at `0x140194e8b`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140194bf5`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140195190`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140194bf5`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140195190`
- `ntoskrnl!EtwActivityIdControl` at `0x1401951ac`
- `ntoskrnl!EtwActivityIdControl` at `0x1401951ac`

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
    if ( (unsigned int)dword_140292E08 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140292E08, 0x200000000004LL) )
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
        (unsigned int)byte_14026E933,
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
    if ( ((unsigned __int8)*((_DWORD *)v26 + 35) & (unsigned __int8)v11) != 0 && (unsigned int)dword_140292E08 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_140292E08, 0x200000000004LL) )
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
          (unsigned int)&word_14026E8A6,
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
0x140194b70  push    rbx
0x140194b72  push    rsi
0x140194b73  push    rdi
0x140194b74  push    r12
0x140194b76  push    r13
0x140194b78  push    r14
0x140194b7a  push    r15
0x140194b7c  sub     rsp, 120h
0x140194b83  mov     rax, cs:__security_cookie
0x140194b8a  xor     rax, rsp
0x140194b8d  mov     [rsp+158h+var_40], rax
0x140194b95  mov     [rsp+158h+var_E4], r9d
0x140194b9a  mov     [rsp+158h+var_70], r8
0x140194ba2  mov     rbx, rcx
0x140194ba5  mov     [rsp+158h+Address], rcx
0x140194bad  mov     [rsp+158h+var_D8], rdx
0x140194bb5  mov     rax, [rsp+158h+arg_20]
0x140194bbd  mov     [rsp+158h+var_C0], rax
0x140194bc5  mov     rax, [rsp+158h+arg_30]
0x140194bcd  mov     [rsp+158h+var_68], rax
0x140194bd5  xorps   xmm0, xmm0
0x140194bd8  movups  xmmword ptr [rsp+158h+ActivityId.Data1], xmm0
0x140194be0  mov     rax, 0FFFFF78000000320h
0x140194bea  mov     rax, [rax]
0x140194bed  mov     [rsp+158h+var_78], rax
0x140194bf5  call    cs:__imp_KeQueryTimeIncrement
0x140194bfc  nop     dword ptr [rax+rax+00h]
0x140194c01  mov     [rsp+158h+var_D0], eax
0x140194c08  xor     edx, edx
0x140194c0a  mov     esi, edx
0x140194c0c  lea     rcx, [rsp+158h+BugCheckParameter2]
0x140194c14  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194c19  lea     rcx, [rsp+158h+var_B0]
0x140194c21  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194c26  mov     rcx, [rsp+158h+Address]
0x140194c2e  test    rcx, rcx
0x140194c31  jz      loc_140194D9E
0x140194c37  lea     r13d, [rdx+10h]
0x140194c3b  mov     [rsp+158h+var_60], r13
0x140194c43  mov     rcx, [rsp+158h+Address]; Address
0x140194c4b  lea     r14d, [rdx+1]
0x140194c4f  mov     [rsp+158h+var_60], r14
0x140194c57  mov     r8d, r14d; Alignment
0x140194c5a  mov     edx, r14d; Length
0x140194c5d  call    cs:__imp_ProbeForRead
0x140194c64  nop     dword ptr [rax+rax+00h]
0x140194c69  movzx   r15d, word ptr [rbx]
0x140194c6d  mov     r12, [rbx+8]
0x140194c71  mov     rdi, r15
0x140194c74  lea     rdx, [r15+12h]; unsigned __int64
0x140194c78  mov     r8d, 73726447h; unsigned int
0x140194c7e  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x140194c83  mov     rsi, rax
0x140194c86  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140194c8a  test    rax, rax
0x140194c8d  jz      loc_140194F56
0x140194c93  cmp     [rsp+158h+var_88], rbx
0x140194c9b  jz      short loc_140194CC7
0x140194c9d  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140194ca2  mov     [rsp+158h+BugCheckParameter4], rax; BugCheckParameter4
0x140194ca7  mov     r9, rsi; BugCheckParameter3
0x140194caa  lea     r8, [rsp+158h+BugCheckParameter2]; BugCheckParameter2
0x140194cb2  lea     edx, [rbx+13h]; BugCheckParameter1
0x140194cb5  mov     ecx, 164h; BugCheckCode
0x140194cba  call    cs:__imp_KeBugCheckEx
0x140194cc7  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140194ccc  mov     rcx, [rax+178h]
0x140194cd3  mov     [rsp+158h+BugCheckParameter2], rcx
0x140194cdb  lea     rcx, [rsp+158h+BugCheckParameter2]
0x140194ce3  mov     [rax+178h], rcx
0x140194cea  mov     [rsp+158h+var_90], rsi
0x140194cf2  lea     rdx, GreDeleteFastMutex
0x140194cf9  mov     [rsp+158h+var_88], rdx
0x140194d01  lea     rax, [rsi+10h]
0x140194d05  mov     [rsi+8], rax
0x140194d09  mov     [rsi], r15w
0x140194d0d  mov     eax, 2
0x140194d12  add     eax, r15d
0x140194d15  mov     [rsi+2], ax
0x140194d19  xor     edx, edx
0x140194d1b  test    r15w, r15w
0x140194d1f  jz      short loc_140194D6D
0x140194d21  mov     r8d, r14d; Alignment
0x140194d24  mov     rdx, rdi; Length
0x140194d27  mov     rcx, r12; Address
0x140194d2a  call    cs:__imp_ProbeForRead
0x140194d31  nop     dword ptr [rax+rax+00h]
0x140194d36  mov     r8, rdi; Size
0x140194d39  mov     rdx, r12; Src
0x140194d3c  mov     rcx, [rsi+8]; void *
0x140194d40  call    memmove
0x140194d45  xor     edx, edx
0x140194d47  jmp     short loc_140194D6D
0x140194d49  lea     rcx, [rsp+158h+var_B0]
0x140194d51  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194d56  lea     rcx, [rsp+158h+BugCheckParameter2]
0x140194d5e  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194d63  mov     eax, 0FFFFFFFBh
0x140194d68  jmp     loc_1401953F5
0x140194d6d  shr     rdi, 1
0x140194d70  mov     rcx, [rsi+8]
0x140194d74  mov     [rcx+rdi*2], dx
0x140194d78  jmp     short loc_140194DAC
0x140194d7a  lea     rcx, [rsp+158h+var_B0]
0x140194d82  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194d87  lea     rcx, [rsp+158h+BugCheckParameter2]
0x140194d8f  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194d94  mov     eax, 0FFFFFFFBh
0x140194d99  jmp     loc_1401953F5
0x140194d9e  mov     r13d, 10h
0x140194da4  lea     r14d, [r13-0Fh]
0x140194da8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140194dac  mov     rdi, rdx
0x140194daf  mov     rax, [rsp+158h+var_D8]
0x140194db7  test    rax, rax
0x140194dba  jz      loc_140194F9B
0x140194dc0  mov     [rsp+158h+var_CC], dx
0x140194dc8  mov     [rsp+158h+var_C8], dx
0x140194dd0  mov     [rsp+158h+var_58], 48h ; 'H'
0x140194ddc  mov     rcx, [rsp+158h+var_D8]; Address
0x140194de4  mov     [rsp+158h+var_58], r14
0x140194dec  mov     r8d, 4; Alignment
0x140194df2  mov     rdx, r14; Length
0x140194df5  call    cs:__imp_ProbeForRead
0x140194dfc  nop     dword ptr [rax+rax+00h]
0x140194e01  mov     rax, [rsp+158h+var_D8]
0x140194e09  movzx   r15d, word ptr [rax+44h]
0x140194e0e  mov     [rsp+158h+var_CC], r15w
0x140194e17  mov     rax, [rsp+158h+var_D8]
0x140194e1f  movzx   r12d, word ptr [rax+46h]
0x140194e24  mov     [rsp+158h+var_C8], r12w
0x140194e2d  mov     ecx, 0BCh; unsigned __int64
0x140194e32  movzx   eax, r15w
0x140194e36  sub     ax, cx
0x140194e39  cmp     ax, 20h ; ' '
0x140194e3d  ja      loc_140194F51
0x140194e43  lea     rdx, [r12+0DCh]; unsigned __int64
0x140194e4b  mov     r8d, 73726447h; unsigned int
0x140194e51  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x140194e56  mov     rdi, rax
0x140194e59  test    rax, rax
0x140194e5c  jz      loc_140194F56
0x140194e62  cmp     [rsp+158h+var_A0], rbx
0x140194e6a  jz      short loc_140194E98
0x140194e6c  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140194e71  mov     [rsp+158h+BugCheckParameter4], rax; BugCheckParameter4
0x140194e76  mov     r9, rdi; BugCheckParameter3
0x140194e79  lea     r8, [rsp+158h+var_B0]; BugCheckParameter2
0x140194e81  mov     edx, 12h; BugCheckParameter1
0x140194e86  mov     ecx, 164h; BugCheckCode
0x140194e8b  call    cs:__imp_KeBugCheckEx
0x140194e98  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140194e9d  mov     rcx, [rax+178h]
0x140194ea4  mov     [rsp+158h+var_B0], rcx
0x140194eac  lea     rcx, [rsp+158h+var_B0]
0x140194eb4  mov     [rax+178h], rcx
0x140194ebb  mov     [rsp+158h+var_A8], rdi
0x140194ec3  lea     rax, GreDeleteFastMutex
0x140194eca  mov     [rsp+158h+var_A0], rax
0x140194ed2  lea     edx, [r15+r12]; Length
0x140194ed6  mov     r8d, 4; Alignment
0x140194edc  mov     rcx, [rsp+158h+var_D8]; Address
0x140194ee4  call    cs:__imp_ProbeForRead
0x140194eeb  nop     dword ptr [rax+rax+00h]
0x140194ef0  mov     rdx, [rsp+158h+var_D8]; Src
0x140194ef8  mov     r8, r15; Size
0x140194efb  mov     rcx, rdi; void *
0x140194efe  call    memmove
0x140194f03  mov     rdx, [rsp+158h+var_D8]
0x140194f0b  add     rdx, r15; Src
0x140194f0e  lea     rcx, [rdi+0DCh]; void *
0x140194f15  mov     r8, r12; Size
0x140194f18  call    memmove
0x140194f1d  mov     eax, 0DCh
0x140194f22  mov     [rdi+44h], ax
0x140194f26  mov     [rdi+46h], r12w
0x140194f2b  jmp     short loc_140194F9B
0x140194f2d  lea     rcx, [rsp+158h+var_B0]
0x140194f35  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194f3a  lea     rcx, [rsp+158h+BugCheckParameter2]
0x140194f42  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194f47  mov     eax, 0FFFFFFFEh
0x140194f4c  jmp     loc_1401953F5
0x140194f51  mov     ebx, 0FFFFFFFEh
0x140194f56  lea     rcx, [rsp+158h+var_B0]
0x140194f5e  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194f63  lea     rcx, [rsp+158h+BugCheckParameter2]
0x140194f6b  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194f70  mov     eax, ebx
0x140194f72  jmp     loc_1401953F5
0x140194f77  lea     rcx, [rsp+158h+var_B0]
0x140194f7f  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194f84  lea     rcx, [rsp+158h+BugCheckParameter2]
0x140194f8c  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x140194f91  mov     eax, 0FFFFFFFEh
0x140194f96  jmp     loc_1401953F5
0x140194f9b  mov     rax, [rsp+158h+var_68]
0x140194fa3  mov     [rsp+158h+var_128], rax; struct _DXGK_DISPLAY_SCENARIO_CONTEXT *
0x140194fa8  mov     eax, [rsp+158h+arg_28]
0x140194faf  mov     [rsp+158h+var_130], eax; enum _MODE
0x140194fb3  mov     rax, [rsp+158h+var_C0]
0x140194fbb  mov     [rsp+158h+BugCheckParameter4], rax; void *
0x140194fc0  mov     r9d, [rsp+158h+var_E4]; unsigned int
0x140194fc5  mov     r8, [rsp+158h+var_70]; struct tagDESKTOP *
0x140194fcd  mov     rdx, rdi; struct _devicemodeW *
0x140194fd0  mov     rcx, rsi; struct _UNICODE_STRING *
0x140194fd3  call    ?xxxUserChangeDisplaySettingsInternal@@YAJPEAU_UNICODE_STRING@@PEAU_devicemodeW@@PEAUtagDESKTOP@@KPEAXW4_MODE@@PEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z; xxxUserChangeDisplaySettingsInternal(_UNICODE_STRING *,_devicemodeW *,tagDESKTOP *,ulong,void *,_MODE,_DXGK_DISPLAY_SCENARIO_CONTEXT *)
0x140194fd8  mov     r15d, eax
0x140194fdb  mov     [rsp+158h+var_E0], eax
0x140194fdf  mov     edx, 90h; unsigned __int64
0x140194fe4  lea     ecx, [rdx+70h]; unsigned __int64
0x140194fe7  mov     r8d, 64437355h; unsigned int
0x140194fed  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x140194ff2  mov     rbx, rax
0x140194ff5  xor     r10d, r10d
0x140194ff8  test    rax, rax
0x140194ffb  jz      loc_1401953D8
0x140195001  mov     r12d, [rsp+158h+var_D0]
0x140195009  imul    r12, [rsp+158h+var_78]
0x140195012  mov     dword ptr [rax], 4
0x140195018  mov     dword ptr [rax+4], 90h
0x14019501f  mov     [rax+28h], r10d
0x140195023  mov     [rax+20h], r10
0x140195027  xor     eax, eax
0x140195029  mov     [rbx+8], rax
0x14019502d  xorps   xmm0, xmm0
0x140195030  movups  xmmword ptr [rbx+10h], xmm0
0x140195034  mov     [rbx+38h], r12
0x140195038  mov     rax, [rsp+158h+var_D8]
0x140195040  test    rax, rax
0x140195043  jz      short loc_14019504D
0x140195045  test    rdi, rdi
0x140195048  mov     ecx, r14d
0x14019504b  jnz     short loc_140195050
0x14019504d  mov     ecx, r10d
0x140195050  mov     eax, [rbx+8Ch]
0x140195056  and     eax, 0FFFFFFFEh
0x140195059  or      eax, ecx
0x14019505b  mov     [rbx+8Ch], eax
0x140195061  mov     rax, [rsp+158h+Address]
0x140195069  test    rax, rax
0x14019506c  jz      short loc_140195084
0x14019506e  test    rsi, rsi
0x140195071  jz      short loc_140195084
0x140195073  cmp     [rsi], r10w
0x140195077  jbe     short loc_140195084
0x140195079  cmp     [rsi+8], r10
0x14019507d  mov     eax, 2
0x140195082  jnz     short loc_140195087
0x140195084  mov     eax, r10d
0x140195087  mov     edx, [rbx+8Ch]
0x14019508d  and     edx, 0FFFFFFFDh
0x140195090  or      edx, eax
0x140195092  and     edx, 0FFFFFFFBh
0x140195095  mov     eax, [rsp+158h+arg_28]
0x14019509c  neg     eax
0x14019509e  sbb     ecx, ecx
0x1401950a0  not     ecx
0x1401950a2  and     ecx, 4
0x1401950a5  or      edx, ecx
0x1401950a7  and     edx, 0FFFFFFF7h
0x1401950aa  neg     [rsp+158h+var_C0]
0x1401950b2  sbb     eax, eax
0x1401950b4  not     eax
0x1401950b6  and     eax, 8
0x1401950b9  or      edx, eax
0x1401950bb  mov     [rbx+8Ch], edx
0x1401950c1  mov     eax, [rsp+158h+var_E4]
0x1401950c5  mov     [rbx+30h], eax
0x1401950c8  mov     [rbx+34h], r15d
0x1401950cc  test    dl, 2
0x1401950cf  jz      short loc_140195117
0x1401950d1  mov     ecx, 7FFFFFFEh
0x1401950d6  mov     rdx, [rsi+8]
0x1401950da  lea     rax, [rbx+6Ch]
0x1401950de  test    rcx, rcx
0x1401950e1  jz      short loc_140195101
0x1401950e3  movzx   r8d, word ptr [rdx]
0x1401950e7  test    r8w, r8w
0x1401950eb  jz      short loc_140195101
0x1401950ed  add     rdx, 2
0x1401950f1  mov     [rax], r8w
0x1401950f5  add     rax, 2
0x1401950f9  sub     rcx, r14
0x1401950fc  sub     r13, r14
0x1401950ff  jnz     short loc_1401950DE
0x140195101  lea     rcx, [rax-2]
0x140195105  test    r13, r13
0x140195108  cmovnz  rcx, rax
0x14019510c  mov     [rcx], r10w
0x140195110  jnz     short loc_140195117
0x140195112  mov     [rbx+6Ch], r10w
0x140195117  mov     eax, [rbx+8Ch]
0x14019511d  test    r14b, al
0x140195120  jz      short loc_14019517B
0x140195122  mov     eax, 0B4h
0x140195127  cmp     [rdi+44h], ax
0x14019512b  jb      short loc_14019517B
0x14019512d  mov     eax, [rdi+48h]
0x140195130  mov     [rbx+40h], eax
  ... truncated ...
```
