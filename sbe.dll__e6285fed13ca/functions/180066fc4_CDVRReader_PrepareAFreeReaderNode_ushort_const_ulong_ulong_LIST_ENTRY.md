# CDVRReader::PrepareAFreeReaderNode(ushort const *,ulong,ulong,_LIST_ENTRY * &)

- ea: `0x180066fc4`
- end: `0x180067304`
- name: `?PrepareAFreeReaderNode@CDVRReader@@IEAAJPEBGKKAEAPEAU_LIST_ENTRY@@@Z`
- size: `832`
- prototype: `__int64 __fastcall(CDVRReader *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, struct _LIST_ENTRY **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180063fbc`
- `0x180065380`

## callees

- `0x1800017a0`
- `0x1800017e0`
- `0x180001c00`
- `0x18005faec`
- `0x180063100`
- `0x180063e34`
- `0x180066fc4`
- `0x180067340`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x180067263`
- `KERNEL32!ResetEvent` at `0x180067263`
- `KERNEL32!InitializeCriticalSection` at `0x1800671a7`
- `KERNEL32!InitializeCriticalSection` at `0x1800671a7`
- `KERNEL32!GetLastError` at `0x180067289`
- `KERNEL32!GetLastError` at `0x180067289`
- `KERNEL32!QueueUserWorkItem` at `0x18006727f`
- `KERNEL32!QueueUserWorkItem` at `0x18006727f`
- `sbeio!DVRCreateDVRFileSource` at `0x1800670f5`
- `sbeio!DVRCreateDVRFileSource` at `0x1800670f5`

## pseudocode

```c
__int64 __fastcall CDVRReader::PrepareAFreeReaderNode(
        LONG *this,
        const unsigned __int16 *a2,
        int a3,
        unsigned int a4,
        struct _LIST_ENTRY **a5)
{
  CDVRReader::ASF_READER_NODE *v8; // rax
  unsigned __int64 v9; // rdx
  CDVRReader::ASF_READER_NODE *v10; // rdi
  __int64 v11; // rax
  struct _RTL_CRITICAL_SECTION *v12; // rsi
  __int64 v13; // r8
  void *v14; // rdx
  LONG v15; // ecx
  LONG v16; // eax
  signed int LastError; // eax
  int v19; // [rsp+40h] [rbp-68h] BYREF
  CDVRReader::ASF_READER_NODE *v20; // [rsp+48h] [rbp-60h]
  struct _LIST_ENTRY **v21; // [rsp+50h] [rbp-58h]
  const unsigned __int16 *v22; // [rsp+58h] [rbp-50h]
  __int64 v23; // [rsp+60h] [rbp-48h] BYREF
  __int64 v24; // [rsp+68h] [rbp-40h] BYREF
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp-38h] BYREF

  v22 = a2;
  v21 = a5;
  v25 = 0;
  v23 = 0;
  v20 = 0;
  v19 = 0;
  v8 = (CDVRReader::ASF_READER_NODE *)operator new(0x58u);
  if ( v8 )
    v10 = CDVRReader::ASF_READER_NODE::ASF_READER_NODE(v8, &v19);
  else
    v10 = 0;
  v20 = v10;
  if ( !v10 )
  {
    v19 = -2147024882;
    goto LABEL_27;
  }
  if ( v19 >= 0 )
  {
    if ( this[119] )
    {
      v19 = (**(__int64 (__fastcall ***)(CDVRReader *, GUID *, __int64 *))this)(
              (CDVRReader *)this,
              &IID_IDVRSourceAdviseSink,
              &v23);
      if ( v19 < 0 )
        goto LABEL_27;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      v11 = v23;
    }
    else
    {
      v11 = 0;
      v23 = 0;
    }
    v19 = DVRCreateDVRFileSource(
            *((_QWORD *)this + 19),
            *((_QWORD *)this + 20),
            (unsigned int)this[112],
            *((_QWORD *)this + 57),
            this[70],
            &v25,
            v11);
    if ( v19 >= 0 )
    {
      *((_QWORD *)v10 + 3) = v25;
      if ( !*((_QWORD *)this + 21) )
        goto LABEL_20;
      v24 = 0;
      v19 = (**v25)(v25, &IID_IDVRFileSource2, &v24);
      if ( v19 < 0 )
        goto LABEL_27;
      v12 = (struct _RTL_CRITICAL_SECTION *)operator new(0x60u);
      if ( v12 )
      {
        v13 = *((_QWORD *)this + 32);
        v14 = (void *)*((_QWORD *)this + 21);
        v15 = this[45];
        v16 = this[44];
        v12->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CPVRAsyncReaderCOM::`vftable';
        v12->LockCount = v16;
        v12->RecursionCount = v15;
        v12->OwningThread = v14;
        LODWORD(v12->LockSemaphore) = 0;
        v12->SpinCount = 0;
        v12[2].DebugInfo = 0;
        *(_QWORD *)&v12[2].LockCount = v13;
        InitializeCriticalSection(v12 + 1);
        _InterlockedIncrement((volatile signed __int32 *)v12->OwningThread + 46);
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)&v12[2].LockCount + 24LL));
      }
      else
      {
        v12 = 0;
      }
      if ( !v12 )
      {
        v19 = -2147024882;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        goto LABEL_27;
      }
      ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v12->DebugInfo->CriticalSection)(v12);
      v19 = (*(__int64 (__fastcall **)(__int64, struct _RTL_CRITICAL_SECTION *))(*(_QWORD *)v24 + 80LL))(v24, v12);
      ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v12->DebugInfo->ProcessLocksList.Flink)(v12);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      if ( v19 >= 0 )
      {
LABEL_20:
        *((_DWORD *)v10 + 12) = a4;
        *((_DWORD *)v10 + 19) = a3;
        *((_DWORD *)v10 + 18) = 0;
        operator delete(*((void **)v10 + 5), v9);
        *((_QWORD *)v10 + 5) = v22;
        *((_QWORD *)v10 + 10) = *((_QWORD *)this + 61);
        ResetEvent(*((HANDLE *)v10 + 8));
        if ( a4 <= 1 )
        {
          CDVRReader::ProcessOpenRequest(v10);
        }
        else if ( !QueueUserWorkItem(CDVRReader::ProcessOpenRequest, v10, 0x10u) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v19 = LastError;
          goto LABEL_27;
        }
        v19 = 0;
      }
    }
  }
LABEL_27:
  if ( v19 >= 0 )
  {
    *a5 = (struct _LIST_ENTRY *)v10;
  }
  else
  {
    *a5 = 0;
    if ( v10 )
      CDVRReader::ASF_READER_NODE::`scalar deleting destructor'(v10, v9);
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180066fc4  mov     r11, rsp
0x180066fc7  mov     [r11+10h], rbx
0x180066fcb  mov     [r11+18h], rsi
0x180066fcf  push    rdi
0x180066fd0  push    r12
0x180066fd2  push    r13
0x180066fd4  push    r14
0x180066fd6  push    r15
0x180066fd8  sub     rsp, 80h
0x180066fdf  mov     rax, cs:__security_cookie
0x180066fe6  xor     rax, rsp
0x180066fe9  mov     [rsp+0A8h+var_30], rax
0x180066fee  mov     r12d, r9d
0x180066ff1  mov     r13d, r8d
0x180066ff4  mov     [rsp+0A8h+var_50], rdx
0x180066ff9  mov     r14, rcx
0x180066ffc  mov     r15, [rsp+0A8h+arg_20]
0x180067004  mov     [rsp+0A8h+var_58], r15
0x180067009  mov     [rsp+0A8h+var_68], 80004005h
0x180067011  xor     ebx, ebx
0x180067013  mov     [r11-60h], rbx
0x180067017  mov     [r11-38h], rbx
0x18006701b  mov     [r11-48h], rbx
0x18006701f  mov     [r11-60h], rbx
0x180067023  mov     [rsp+0A8h+var_68], ebx
0x180067027  lea     ecx, [rbx+58h]; Size
0x18006702a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006702f  test    rax, rax
0x180067032  jz      short loc_180067046
0x180067034  lea     rdx, [rsp+0A8h+var_68]; int *
0x180067039  mov     rcx, rax; this
0x18006703c  call    ??0ASF_READER_NODE@CDVRReader@@QEAA@PEAJ@Z; CDVRReader::ASF_READER_NODE::ASF_READER_NODE(long *)
0x180067041  mov     rdi, rax
0x180067044  jmp     short loc_180067049
0x180067046  mov     rdi, rbx
0x180067049  mov     [rsp+0A8h+var_60], rdi
0x18006704e  test    rdi, rdi
0x180067051  jnz     short loc_180067060
0x180067053  mov     [rsp+0A8h+var_68], 8007000Eh
0x18006705b  jmp     loc_1800672AD
0x180067060  mov     eax, [rsp+0A8h+var_68]
0x180067064  test    eax, eax
0x180067066  js      loc_1800672AD
0x18006706c  cmp     [r14+1DCh], ebx
0x180067073  jz      short loc_1800670B7
0x180067075  mov     rax, [r14]
0x180067078  lea     r8, [rsp+0A8h+var_48]
0x18006707d  lea     rdx, IID_IDVRSourceAdviseSink
0x180067084  mov     rcx, r14
0x180067087  mov     rax, [rax]
0x18006708a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006708f  mov     [rsp+0A8h+var_68], eax
0x180067093  mov     eax, [rsp+0A8h+var_68]
0x180067097  test    eax, eax
0x180067099  js      loc_1800672AD
0x18006709f  mov     rcx, [rsp+0A8h+var_48]
0x1800670a4  mov     rax, [rcx]
0x1800670a7  mov     rax, [rax+10h]
0x1800670ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800670b0  mov     rax, [rsp+0A8h+var_48]
0x1800670b5  jmp     short loc_1800670BF
0x1800670b7  mov     rax, rbx
0x1800670ba  mov     [rsp+0A8h+var_48], rbx
0x1800670bf  mov     [rsp+0A8h+var_78], rax
0x1800670c4  lea     rax, [rsp+0A8h+var_38]
0x1800670c9  mov     [rsp+0A8h+var_80], rax
0x1800670ce  mov     eax, [r14+118h]
0x1800670d5  mov     [rsp+0A8h+var_88], eax
0x1800670d9  mov     r9, [r14+1C8h]
0x1800670e0  mov     r8d, [r14+1C0h]
0x1800670e7  mov     rdx, [r14+0A0h]
0x1800670ee  mov     rcx, [r14+98h]
0x1800670f5  call    cs:__imp_DVRCreateDVRFileSource
0x1800670fb  mov     [rsp+0A8h+var_68], eax
0x1800670ff  mov     eax, [rsp+0A8h+var_68]
0x180067103  test    eax, eax
0x180067105  js      loc_1800672AD
0x18006710b  mov     rax, [rsp+0A8h+var_38]
0x180067110  mov     [rdi+18h], rax
0x180067114  cmp     [r14+0A8h], rbx
0x18006711b  jz      loc_180067237
0x180067121  mov     rcx, [rsp+0A8h+var_38]
0x180067126  mov     [rsp+0A8h+var_40], rbx
0x18006712b  mov     rax, [rcx]
0x18006712e  lea     r8, [rsp+0A8h+var_40]
0x180067133  lea     rdx, IID_IDVRFileSource2
0x18006713a  mov     rax, [rax]
0x18006713d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067142  mov     [rsp+0A8h+var_68], eax
0x180067146  mov     eax, [rsp+0A8h+var_68]
0x18006714a  test    eax, eax
0x18006714c  js      loc_1800672AD
0x180067152  mov     ecx, 60h ; '`'; Size
0x180067157  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006715c  mov     rsi, rax
0x18006715f  test    rax, rax
0x180067162  jz      short loc_1800671C2
0x180067164  mov     r8, [r14+100h]
0x18006716b  mov     rdx, [r14+0A8h]
0x180067172  mov     ecx, [r14+0B4h]
0x180067179  mov     eax, [r14+0B0h]
0x180067180  lea     r9, ??_7CPVRAsyncReaderCOM@@6B@; const CPVRAsyncReaderCOM::`vftable'
0x180067187  mov     [rsi], r9
0x18006718a  mov     [rsi+8], eax
0x18006718d  mov     [rsi+0Ch], ecx
0x180067190  mov     [rsi+10h], rdx
0x180067194  mov     [rsi+18h], ebx
0x180067197  mov     [rsi+20h], rbx
0x18006719b  mov     [rsi+50h], rbx
0x18006719f  mov     [rsi+58h], r8
0x1800671a3  lea     rcx, [rsi+28h]; lpCriticalSection
0x1800671a7  call    cs:__imp_InitializeCriticalSection
0x1800671ad  mov     rax, [rsi+10h]
0x1800671b1  lock inc dword ptr [rax+0B8h]
0x1800671b8  mov     rax, [rsi+58h]
0x1800671bc  lock inc dword ptr [rax+18h]
0x1800671c0  jmp     short loc_1800671C5
0x1800671c2  mov     rsi, rbx
0x1800671c5  test    rsi, rsi
0x1800671c8  jnz     short loc_1800671E8
0x1800671ca  mov     [rsp+0A8h+var_68], 8007000Eh
0x1800671d2  mov     rcx, [rsp+0A8h+var_40]
0x1800671d7  mov     rax, [rcx]
0x1800671da  mov     rax, [rax+10h]
0x1800671de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800671e3  jmp     loc_1800672AD
0x1800671e8  mov     rax, [rsi]
0x1800671eb  mov     rcx, rsi
0x1800671ee  mov     rax, [rax+8]
0x1800671f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800671f7  mov     rcx, [rsp+0A8h+var_40]
0x1800671fc  mov     rax, [rcx]
0x1800671ff  mov     rdx, rsi
0x180067202  mov     rax, [rax+50h]
0x180067206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006720b  mov     [rsp+0A8h+var_68], eax
0x18006720f  mov     rax, [rsi]
0x180067212  mov     rcx, rsi
0x180067215  mov     rax, [rax+10h]
0x180067219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006721e  mov     rcx, [rsp+0A8h+var_40]
0x180067223  mov     rax, [rcx]
0x180067226  mov     rax, [rax+10h]
0x18006722a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006722f  mov     eax, [rsp+0A8h+var_68]
0x180067233  test    eax, eax
0x180067235  js      short loc_1800672AD
0x180067237  mov     [rdi+30h], r12d
0x18006723b  mov     [rdi+4Ch], r13d
0x18006723f  mov     [rdi+48h], ebx
0x180067242  mov     rcx, [rdi+28h]; void *
0x180067246  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006724b  mov     rax, [rsp+0A8h+var_50]
0x180067250  mov     [rdi+28h], rax
0x180067254  mov     rax, [r14+1E8h]
0x18006725b  mov     [rdi+50h], rax
0x18006725f  mov     rcx, [rdi+40h]; hEvent
0x180067263  call    cs:__imp_ResetEvent
0x180067269  cmp     r12d, 1
0x18006726d  jbe     short loc_1800672A1
0x18006726f  mov     r8d, 10h; Flags
0x180067275  mov     rdx, rdi; Context
0x180067278  lea     rcx, ?ProcessOpenRequest@CDVRReader@@KAKPEAX@Z; Function
0x18006727f  call    cs:__imp_QueueUserWorkItem
0x180067285  test    eax, eax
0x180067287  jnz     short loc_1800672A9
0x180067289  call    cs:__imp_GetLastError
0x18006728f  test    eax, eax
0x180067291  jle     short loc_18006729B
0x180067293  movzx   eax, ax
0x180067296  or      eax, 80070000h
0x18006729b  mov     [rsp+0A8h+var_68], eax
0x18006729f  jmp     short loc_1800672AD
0x1800672a1  mov     rcx, rdi; lpThreadParameter
0x1800672a4  call    ?ProcessOpenRequest@CDVRReader@@KAKPEAX@Z; CDVRReader::ProcessOpenRequest(void *)
0x1800672a9  mov     [rsp+0A8h+var_68], ebx
0x1800672ad  jmp     short loc_1800672BB
0x1800672af  xor     ebx, ebx
0x1800672b1  mov     rdi, [rsp+0A8h+var_60]
0x1800672b6  mov     r15, [rsp+0A8h+var_58]
0x1800672bb  cmp     [rsp+0A8h+var_68], ebx
0x1800672bf  jge     short loc_1800672D3
0x1800672c1  mov     [r15], rbx
0x1800672c4  test    rdi, rdi
0x1800672c7  jz      short loc_1800672D6
0x1800672c9  mov     rcx, rdi; this
0x1800672cc  call    ??_GASF_READER_NODE@CDVRReader@@QEAAPEAXI@Z; CDVRReader::ASF_READER_NODE::`scalar deleting destructor'(uint)
0x1800672d1  jmp     short loc_1800672D6
0x1800672d3  mov     [r15], rdi
0x1800672d6  mov     eax, [rsp+0A8h+var_68]
0x1800672da  mov     rcx, [rsp+0A8h+var_30]
0x1800672df  xor     rcx, rsp; StackCookie
0x1800672e2  call    __security_check_cookie
0x1800672e7  lea     r11, [rsp+0A8h+var_28]
0x1800672ef  mov     rbx, [r11+38h]
0x1800672f3  mov     rsi, [r11+40h]
0x1800672f7  mov     rsp, r11
0x1800672fa  pop     r15
0x1800672fc  pop     r14
0x1800672fe  pop     r13
0x180067300  pop     r12
0x180067302  pop     rdi
0x180067303  retn
0x1800b3a54  push    rbp
0x1800b3a56  sub     rsp, 40h
0x1800b3a5a  mov     rbp, rdx
0x1800b3a5d  lea     rdx, [rbp+40h]; int *
0x1800b3a61  call    ?SBE_DelayLoadDllExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@PEAJ@Z; SBE_DelayLoadDllExceptionFilter(_EXCEPTION_POINTERS *,long *)
0x1800b3a66  nop
0x1800b3a67  add     rsp, 40h
0x1800b3a6b  pop     rbp
0x1800b3a6c  retn
0x1800b3a6e  push    rbp
0x1800b3a70  sub     rsp, 40h
0x1800b3a74  mov     rbp, rdx
0x1800b3a77  mov     rax, [rbp+50h]
0x1800b3a7b  mov     rcx, [rbp+48h]; this
0x1800b3a7f  cmp     dword ptr [rbp+40h], 0
0x1800b3a83  jge     short loc_1800B3A98
0x1800b3a85  mov     qword ptr [rax], 0
0x1800b3a8c  test    rcx, rcx
0x1800b3a8f  jz      short loc_1800B3A9B
0x1800b3a91  call    ??_GASF_READER_NODE@CDVRReader@@QEAAPEAXI@Z; CDVRReader::ASF_READER_NODE::`scalar deleting destructor'(uint)
0x1800b3a96  jmp     short loc_1800B3A9B
0x1800b3a98  mov     [rax], rcx
0x1800b3a9b  add     rsp, 40h
0x1800b3a9f  pop     rbp
0x1800b3aa0  retn
```
