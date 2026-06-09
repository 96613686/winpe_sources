# VMX_DISK_DEVICE::Read(unsigned __int64,ulong,uchar * *)

- ea: `0x140034000`
- end: `0x1400341a0`
- name: `?Read@VMX_DISK_DEVICE@@QEAAJ_KKPEAPEAE@Z`
- size: `416`
- prototype: `__int64 __fastcall(VMX_DISK_DEVICE *__hidden this, unsigned __int64, unsigned int, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1400465b0`
- `0x140049704`

## callees

- `0x1400099d8`
- `0x14001b78c`
- `0x14001b960`
- `0x14001b9a0`
- `0x140034000`
- `0x1400476a8`

## import_xrefs

- `ntoskrnl!_ultow_s` at `0x1400340b1`
- `ntoskrnl!_ultow_s` at `0x1400340b1`
- `ntoskrnl!_ui64tow_s` at `0x1400340cf`
- `ntoskrnl!_ui64tow_s` at `0x1400340cf`

## pseudocode

```c
__int64 __fastcall VMX_DISK_DEVICE::Read(VMX_DISK_DEVICE *this, unsigned __int64 a2, ULONG a3, unsigned __int8 **a4)
{
  int v9; // eax
  unsigned int v10; // edi
  wchar_t DstBuf[12]; // [rsp+40h] [rbp-78h] BYREF
  wchar_t v12[20]; // [rsp+58h] [rbp-60h] BYREF

  *a4 = 0;
  if ( *((_DWORD *)this + 10) )
  {
    if ( _InterlockedExchange((volatile __int32 *)this + 11, 1) != 1 )
      VmxpSendRecordedFailureNotification(this);
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 10, WPP_2f8af752156e3401cd435973c831895d_Traceguids, 3221225486LL);
    }
    return 3221225486LL;
  }
  else
  {
    if ( *((_BYTE *)Global + 304) )
    {
      _ultow_s(*((_DWORD *)this + 8), DstBuf, 9u, 16);
      _ui64tow_s(a2, v12, 0x11u, 16);
      (*((void (__fastcall **)(_QWORD, __int64, __int64, const wchar_t *, wchar_t *, wchar_t *))Global + 2))(
        0,
        2151153667LL,
        3,
        L"read",
        DstBuf,
        v12);
    }
    v9 = VmxpRead(*((PDEVICE_OBJECT *)this + 3), (union _LARGE_INTEGER)a2, a3, a4);
    v10 = v9;
    if ( v9 < 0 )
    {
      if ( v9 != -1073741670 && _InterlockedExchange((volatile __int32 *)this + 11, 1) != 1 )
        VmxpSendRecordedFailureNotification(this);
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 11, WPP_2f8af752156e3401cd435973c831895d_Traceguids, v10);
      }
    }
    return v10;
  }
}

```

## disassembly

```asm
0x140034000  push    rbx
0x140034002  push    rbp
0x140034003  push    rsi
0x140034004  push    rdi
0x140034005  sub     rsp, 98h
0x14003400c  mov     rax, cs:__security_cookie
0x140034013  xor     rax, rsp
0x140034016  mov     [rsp+0B8h+var_38], rax
0x14003401e  mov     qword ptr [r9], 0
0x140034025  mov     rdi, r9
0x140034028  cmp     dword ptr [rcx+28h], 0
0x14003402c  mov     ebp, r8d
0x14003402f  mov     rsi, rdx
0x140034032  mov     rbx, rcx
0x140034035  jz      short loc_14003408F
0x140034037  mov     eax, 1
0x14003403c  xchg    eax, [rcx+2Ch]
0x14003403f  cmp     eax, 1
0x140034042  jz      short loc_140034049
0x140034044  call    ?VmxpSendRecordedFailureNotification@@YAXPEAVVMX_DISK_DEVICE@@@Z; VmxpSendRecordedFailureNotification(VMX_DISK_DEVICE *)
0x140034049  mov     rcx, cs:WPP_GLOBAL_Control
0x140034050  lea     rax, WPP_GLOBAL_Control
0x140034057  mov     ebx, 0C000000Eh
0x14003405c  cmp     rcx, rax
0x14003405f  jz      short loc_140034088
0x140034061  test    dword ptr [rcx+2Ch], 100h
0x140034068  jz      short loc_140034088
0x14003406a  cmp     byte ptr [rcx+29h], 2
0x14003406e  jb      short loc_140034088
0x140034070  mov     rcx, [rcx+18h]
0x140034074  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x14003407b  mov     edx, 0Ah
0x140034080  mov     r9d, ebx
0x140034083  call    WPP_SF_d
0x140034088  mov     eax, ebx
0x14003408a  jmp     loc_140034183
0x14003408f  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140034096  cmp     byte ptr [rax+130h], 0
0x14003409d  jz      short loc_140034113
0x14003409f  mov     ecx, [rcx+20h]; Val
0x1400340a2  lea     rdx, [rsp+0B8h+DstBuf]; DstBuf
0x1400340a7  mov     r9d, 10h; Radix
0x1400340ad  lea     r8d, [r9-7]; SizeInWords
0x1400340b1  call    cs:__imp__ultow_s
0x1400340b8  nop     dword ptr [rax+rax+00h]
0x1400340bd  mov     r9d, 10h; Radix
0x1400340c3  lea     rdx, [rsp+0B8h+var_60]; DstBuf
0x1400340c8  mov     rcx, rsi; Val
0x1400340cb  lea     r8d, [r9+1]; SizeInWords
0x1400340cf  call    cs:__imp__ui64tow_s
0x1400340d6  nop     dword ptr [rax+rax+00h]
0x1400340db  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x1400340e2  lea     rcx, [rsp+0B8h+var_60]
0x1400340e7  mov     [rsp+0B8h+var_90], rcx
0x1400340ec  lea     r9, aRead; "read"
0x1400340f3  lea     rcx, [rsp+0B8h+DstBuf]
0x1400340f8  mov     r8d, 3
0x1400340fe  mov     [rsp+0B8h+var_98], rcx
0x140034103  mov     edx, 80380003h
0x140034108  mov     rax, [rax+10h]
0x14003410c  xor     ecx, ecx
0x14003410e  call    _guard_dispatch_icall
0x140034113  mov     rcx, [rbx+18h]; DeviceObject
0x140034117  mov     r9, rdi; unsigned __int8 **
0x14003411a  mov     r8d, ebp; unsigned int
0x14003411d  mov     rdx, rsi; unsigned __int64
0x140034120  call    ?VmxpRead@@YAJPEAU_DEVICE_OBJECT@@_KKPEAPEAE@Z; VmxpRead(_DEVICE_OBJECT *,unsigned __int64,ulong,uchar * *)
0x140034125  mov     edi, eax
0x140034127  test    eax, eax
0x140034129  jns     short loc_140034181
0x14003412b  cmp     eax, 0C000009Ah
0x140034130  jz      short loc_140034147
0x140034132  mov     ecx, 1
0x140034137  xchg    ecx, [rbx+2Ch]
0x14003413a  cmp     ecx, 1
0x14003413d  jz      short loc_140034147
0x14003413f  mov     rcx, rbx; struct VMX_DISK_DEVICE *
0x140034142  call    ?VmxpSendRecordedFailureNotification@@YAXPEAVVMX_DISK_DEVICE@@@Z; VmxpSendRecordedFailureNotification(VMX_DISK_DEVICE *)
0x140034147  mov     rcx, cs:WPP_GLOBAL_Control
0x14003414e  lea     rax, WPP_GLOBAL_Control
0x140034155  cmp     rcx, rax
0x140034158  jz      short loc_140034181
0x14003415a  test    dword ptr [rcx+2Ch], 100h
0x140034161  jz      short loc_140034181
0x140034163  cmp     byte ptr [rcx+29h], 2
0x140034167  jb      short loc_140034181
0x140034169  mov     rcx, [rcx+18h]
0x14003416d  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x140034174  mov     edx, 0Bh
0x140034179  mov     r9d, edi
0x14003417c  call    WPP_SF_d
0x140034181  mov     eax, edi
0x140034183  mov     rcx, [rsp+0B8h+var_38]
0x14003418b  xor     rcx, rsp; StackCookie
0x14003418e  call    __security_check_cookie
0x140034193  add     rsp, 98h
0x14003419a  pop     rdi
0x14003419b  pop     rsi
0x14003419c  pop     rbp
0x14003419d  pop     rbx
0x14003419e  retn
```
