# VMX_DISK_DEVICE::Write(unsigned __int64,ulong,uchar *)

- ea: `0x14003c4b4`
- end: `0x14003c64d`
- name: `?Write@VMX_DISK_DEVICE@@QEAAJ_KKPEAE@Z`
- size: `409`
- prototype: `__int64 __fastcall(VMX_DISK_DEVICE *__hidden this, unsigned __int64, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140047e38`
- `0x14004a178`

## callees

- `0x1400099d8`
- `0x14001b78c`
- `0x14001b960`
- `0x14001b9a0`
- `0x14003c4b4`
- `0x14004794c`

## import_xrefs

- `ntoskrnl!_ultow_s` at `0x14003c55e`
- `ntoskrnl!_ultow_s` at `0x14003c55e`
- `ntoskrnl!_ui64tow_s` at `0x14003c57c`
- `ntoskrnl!_ui64tow_s` at `0x14003c57c`

## string_xrefs

- `0x14003c599`: `write`

## pseudocode

```c
__int64 __fastcall VMX_DISK_DEVICE::Write(
        VMX_DISK_DEVICE *this,
        unsigned __int64 a2,
        unsigned int a3,
        unsigned __int8 *a4)
{
  int v9; // eax
  unsigned int v10; // edi
  wchar_t DstBuf[12]; // [rsp+40h] [rbp-78h] BYREF
  wchar_t v12[20]; // [rsp+58h] [rbp-60h] BYREF

  if ( *((_DWORD *)this + 10) )
  {
    if ( _InterlockedExchange((volatile __int32 *)this + 11, 1) != 1 )
      VmxpSendRecordedFailureNotification(this);
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 12, WPP_2f8af752156e3401cd435973c831895d_Traceguids, 3221225486LL);
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
        L"write",
        DstBuf,
        v12);
    }
    v9 = VmxpWrite(*((PDEVICE_OBJECT *)this + 3), a2, a3, a4);
    v10 = v9;
    if ( v9 < 0 )
    {
      if ( v9 != -1073741670 && _InterlockedExchange((volatile __int32 *)this + 11, 1) != 1 )
        VmxpSendRecordedFailureNotification(this);
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 13, WPP_2f8af752156e3401cd435973c831895d_Traceguids, v10);
      }
    }
    return v10;
  }
}

```

## disassembly

```asm
0x14003c4b4  push    rbx
0x14003c4b6  push    rbp
0x14003c4b7  push    rsi
0x14003c4b8  push    rdi
0x14003c4b9  sub     rsp, 98h
0x14003c4c0  mov     rax, cs:__security_cookie
0x14003c4c7  xor     rax, rsp
0x14003c4ca  mov     [rsp+0B8h+var_38], rax
0x14003c4d2  cmp     dword ptr [rcx+28h], 0
0x14003c4d6  mov     rbp, r9
0x14003c4d9  mov     esi, r8d
0x14003c4dc  mov     rdi, rdx
0x14003c4df  mov     rbx, rcx
0x14003c4e2  jz      short loc_14003C53C
0x14003c4e4  mov     eax, 1
0x14003c4e9  xchg    eax, [rcx+2Ch]
0x14003c4ec  cmp     eax, 1
0x14003c4ef  jz      short loc_14003C4F6
0x14003c4f1  call    ?VmxpSendRecordedFailureNotification@@YAXPEAVVMX_DISK_DEVICE@@@Z; VmxpSendRecordedFailureNotification(VMX_DISK_DEVICE *)
0x14003c4f6  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c4fd  lea     rax, WPP_GLOBAL_Control
0x14003c504  mov     ebx, 0C000000Eh
0x14003c509  cmp     rcx, rax
0x14003c50c  jz      short loc_14003C535
0x14003c50e  test    dword ptr [rcx+2Ch], 100h
0x14003c515  jz      short loc_14003C535
0x14003c517  cmp     byte ptr [rcx+29h], 2
0x14003c51b  jb      short loc_14003C535
0x14003c51d  mov     rcx, [rcx+18h]
0x14003c521  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x14003c528  mov     edx, 0Ch
0x14003c52d  mov     r9d, ebx
0x14003c530  call    WPP_SF_d
0x14003c535  mov     eax, ebx
0x14003c537  jmp     loc_14003C630
0x14003c53c  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14003c543  cmp     byte ptr [rax+130h], 0
0x14003c54a  jz      short loc_14003C5C0
0x14003c54c  mov     ecx, [rcx+20h]; Val
0x14003c54f  lea     rdx, [rsp+0B8h+DstBuf]; DstBuf
0x14003c554  mov     r9d, 10h; Radix
0x14003c55a  lea     r8d, [r9-7]; SizeInWords
0x14003c55e  call    cs:__imp__ultow_s
0x14003c565  nop     dword ptr [rax+rax+00h]
0x14003c56a  mov     r9d, 10h; Radix
0x14003c570  lea     rdx, [rsp+0B8h+var_60]; DstBuf
0x14003c575  mov     rcx, rdi; Val
0x14003c578  lea     r8d, [r9+1]; SizeInWords
0x14003c57c  call    cs:__imp__ui64tow_s
0x14003c583  nop     dword ptr [rax+rax+00h]
0x14003c588  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14003c58f  lea     rcx, [rsp+0B8h+var_60]
0x14003c594  mov     [rsp+0B8h+var_90], rcx
0x14003c599  lea     r9, aWrite; "write"
0x14003c5a0  lea     rcx, [rsp+0B8h+DstBuf]
0x14003c5a5  mov     r8d, 3
0x14003c5ab  mov     [rsp+0B8h+var_98], rcx
0x14003c5b0  mov     edx, 80380003h
0x14003c5b5  mov     rax, [rax+10h]
0x14003c5b9  xor     ecx, ecx
0x14003c5bb  call    _guard_dispatch_icall
0x14003c5c0  mov     rcx, [rbx+18h]; DeviceObject
0x14003c5c4  mov     r9, rbp; unsigned __int8 *
0x14003c5c7  mov     r8d, esi; unsigned int
0x14003c5ca  mov     rdx, rdi; unsigned __int64
0x14003c5cd  call    ?VmxpWrite@@YAJPEAU_DEVICE_OBJECT@@_KKPEAE@Z; VmxpWrite(_DEVICE_OBJECT *,unsigned __int64,ulong,uchar *)
0x14003c5d2  mov     edi, eax
0x14003c5d4  test    eax, eax
0x14003c5d6  jns     short loc_14003C62E
0x14003c5d8  cmp     eax, 0C000009Ah
0x14003c5dd  jz      short loc_14003C5F4
0x14003c5df  mov     ecx, 1
0x14003c5e4  xchg    ecx, [rbx+2Ch]
0x14003c5e7  cmp     ecx, 1
0x14003c5ea  jz      short loc_14003C5F4
0x14003c5ec  mov     rcx, rbx; struct VMX_DISK_DEVICE *
0x14003c5ef  call    ?VmxpSendRecordedFailureNotification@@YAXPEAVVMX_DISK_DEVICE@@@Z; VmxpSendRecordedFailureNotification(VMX_DISK_DEVICE *)
0x14003c5f4  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c5fb  lea     rax, WPP_GLOBAL_Control
0x14003c602  cmp     rcx, rax
0x14003c605  jz      short loc_14003C62E
0x14003c607  test    dword ptr [rcx+2Ch], 100h
0x14003c60e  jz      short loc_14003C62E
0x14003c610  cmp     byte ptr [rcx+29h], 2
0x14003c614  jb      short loc_14003C62E
0x14003c616  mov     rcx, [rcx+18h]
0x14003c61a  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x14003c621  mov     edx, 0Dh
0x14003c626  mov     r9d, edi
0x14003c629  call    WPP_SF_d
0x14003c62e  mov     eax, edi
0x14003c630  mov     rcx, [rsp+0B8h+var_38]
0x14003c638  xor     rcx, rsp; StackCookie
0x14003c63b  call    __security_check_cookie
0x14003c640  add     rsp, 98h
0x14003c647  pop     rdi
0x14003c648  pop     rsi
0x14003c649  pop     rbp
0x14003c64a  pop     rbx
0x14003c64b  retn
```
