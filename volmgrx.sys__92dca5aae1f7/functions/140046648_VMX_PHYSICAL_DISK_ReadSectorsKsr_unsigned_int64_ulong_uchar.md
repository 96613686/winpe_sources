# VMX_PHYSICAL_DISK::ReadSectorsKsr(unsigned __int64,ulong,uchar * *)

- ea: `0x140046648`
- end: `0x1400468a5`
- name: `?ReadSectorsKsr@VMX_PHYSICAL_DISK@@QEAAJ_KKPEAPEAE@Z`
- size: `605`
- prototype: `__int64 __fastcall(VMX_PHYSICAL_DISK *this, unsigned __int64, int, PVOID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1400465b0`

## callees

- `0x14001b960`
- `0x14001b9a0`
- `0x140033ce0`
- `0x140037d24`
- `0x140039a98`
- `0x140046648`

## import_xrefs

- `ntoskrnl!_ultow_s` at `0x1400467c5`
- `ntoskrnl!_ultow_s` at `0x1400467f8`
- `ntoskrnl!_ultow_s` at `0x140046810`
- `ntoskrnl!_ultow_s` at `0x1400467c5`
- `ntoskrnl!_ultow_s` at `0x1400467f8`
- `ntoskrnl!_ultow_s` at `0x140046810`
- `ntoskrnl!_ui64tow_s` at `0x1400467df`
- `ntoskrnl!_ui64tow_s` at `0x1400467df`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046861`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046861`
- `ntoskrnl!ZwClose` at `0x140046876`
- `ntoskrnl!ZwClose` at `0x140046876`

## pseudocode

```c
__int64 __fastcall VMX_PHYSICAL_DISK::ReadSectorsKsr(VMX_PHYSICAL_DISK *this, unsigned __int64 a2, int a3, PVOID *a4)
{
  unsigned __int64 v6; // rdi
  unsigned int v8; // esi
  unsigned int v9; // r14d
  VMX_GLOBAL_DATA *v10; // rax
  signed int DeviceParameterBinary; // ebx
  __int64 v12; // rcx
  unsigned __int64 v13; // rax
  unsigned __int16 *v14; // rdx
  unsigned int v16; // [rsp+40h] [rbp-69h] BYREF
  PVOID P; // [rsp+48h] [rbp-61h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-59h] BYREF
  wchar_t v19; // [rsp+58h] [rbp-51h] BYREF
  wchar_t v20[12]; // [rsp+60h] [rbp-49h] BYREF
  wchar_t DstBuf[12]; // [rsp+78h] [rbp-31h] BYREF
  wchar_t v22[20]; // [rsp+90h] [rbp-19h] BYREF

  v6 = a2;
  v8 = 0;
  v9 = *(_DWORD *)(*((_QWORD *)this + 2) + 36LL);
  v10 = Global;
  *a4 = 0;
  P = 0;
  Handle = 0;
  v16 = 0;
  if ( !*((_BYTE *)v10 + 304) )
  {
    DeviceParameterBinary = -1073741275;
    goto LABEL_22;
  }
  v12 = 0x100000 / v9;
  v13 = *((_QWORD *)this + 8) - v12 + 1;
  if ( a2 > v13 )
    v6 = a2 - v13;
  switch ( v6 )
  {
    case 2uLL:
      goto LABEL_15;
    case 6uLL:
      goto LABEL_12;
    case 0x11uLL:
      goto LABEL_15;
    case 0x740uLL:
LABEL_12:
      DeviceParameterBinary = VMX_DISK_DEVICE::OpenDeviceParameterKey(
                                *((VMX_DISK_DEVICE **)this + 2),
                                0x100000 % v9,
                                &Handle);
      if ( DeviceParameterBinary < 0 )
      {
        v8 = 1;
        goto LABEL_22;
      }
      v14 = L"Header";
      goto LABEL_19;
  }
  if ( v6 != 2045 )
  {
    if ( v6 != 2047 )
    {
      v8 = 3;
      DeviceParameterBinary = -1073741637;
      goto LABEL_22;
    }
    goto LABEL_12;
  }
LABEL_15:
  DeviceParameterBinary = VmxpOpenKsrKey(v12, &Handle);
  if ( DeviceParameterBinary < 0 )
  {
    v8 = 2;
    goto LABEL_22;
  }
  v14 = L"Toc";
  if ( v6 == 17 )
    v14 = L"Config";
LABEL_19:
  v16 = a3 * v9;
  DeviceParameterBinary = VmxpGetDeviceParameterBinary(Handle, v14, &P, &v16);
  if ( DeviceParameterBinary >= 0 )
  {
    *a4 = P;
    P = 0;
  }
  else
  {
    v8 = 4;
  }
LABEL_22:
  if ( *((_BYTE *)Global + 304) && DeviceParameterBinary < 0 )
  {
    _ultow_s(*(_DWORD *)(*((_QWORD *)this + 2) + 32LL), DstBuf, 9u, 16);
    _ui64tow_s(v6, v22, 0x11u, 16);
    _ultow_s(v8, &v19, 2u, 16);
    _ultow_s(DeviceParameterBinary, v20, 9u, 16);
    (*((void (__fastcall **)(_QWORD, __int64, __int64, wchar_t *, wchar_t *, wchar_t *, wchar_t *))Global + 2))(
      0,
      2151153666LL,
      4,
      DstBuf,
      v22,
      &v19,
      v20);
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)DeviceParameterBinary;
}

```

## disassembly

```asm
0x140046648  push    rbp
0x14004664a  push    rbx
0x14004664b  push    rsi
0x14004664c  push    rdi
0x14004664d  push    r12
0x14004664f  push    r13
0x140046651  push    r14
0x140046653  push    r15
0x140046655  lea     rbp, [rsp-1Fh]
0x14004665a  sub     rsp, 0C8h
0x140046661  mov     rax, cs:__security_cookie
0x140046668  xor     rax, rsp
0x14004666b  mov     [rbp+57h+var_48], rax
0x14004666f  mov     rax, [rcx+10h]
0x140046673  xor     ebx, ebx
0x140046675  mov     r12, r9
0x140046678  mov     r13d, r8d
0x14004667b  mov     rdi, rdx
0x14004667e  mov     r15, rcx
0x140046681  mov     esi, ebx
0x140046683  mov     r14d, [rax+24h]
0x140046687  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14004668e  mov     [r9], rbx
0x140046691  mov     [rbp+57h+P], rbx
0x140046695  mov     [rbp+57h+Handle], rbx
0x140046699  mov     [rbp+57h+var_C0], ebx
0x14004669c  cmp     [rax+130h], bl
0x1400466a2  jnz     short loc_1400466AE
0x1400466a4  mov     ebx, 0C0000225h
0x1400466a9  jmp     loc_140046788
0x1400466ae  xor     edx, edx; unsigned __int8
0x1400466b0  mov     eax, 100000h
0x1400466b5  div     r14d
0x1400466b8  mov     ecx, eax; unsigned __int8
0x1400466ba  mov     rax, [r15+40h]
0x1400466be  sub     rax, rcx
0x1400466c1  inc     rax
0x1400466c4  cmp     rdi, rax
0x1400466c7  jbe     short loc_1400466CC
0x1400466c9  sub     rdi, rax
0x1400466cc  mov     rax, rdi
0x1400466cf  sub     rax, 2
0x1400466d3  jz      short loc_140046729
0x1400466d5  sub     rax, 4
0x1400466d9  jz      short loc_140046706
0x1400466db  sub     rax, 0Bh
0x1400466df  jz      short loc_140046729
0x1400466e1  sub     rax, 72Fh
0x1400466e7  jz      short loc_140046706
0x1400466e9  sub     rax, 0BDh
0x1400466ef  jz      short loc_140046729
0x1400466f1  cmp     rax, 2
0x1400466f5  jz      short loc_140046706
0x1400466f7  mov     esi, 3
0x1400466fc  mov     ebx, 0C00000BBh
0x140046701  jmp     loc_140046788
0x140046706  mov     rcx, [r15+10h]; this
0x14004670a  lea     r8, [rbp+57h+Handle]; void **
0x14004670e  call    ?OpenDeviceParameterKey@VMX_DISK_DEVICE@@QEAAJEPEAPEAX@Z; VMX_DISK_DEVICE::OpenDeviceParameterKey(uchar,void * *)
0x140046713  mov     ebx, eax
0x140046715  test    eax, eax
0x140046717  jns     short loc_140046720
0x140046719  mov     esi, 1
0x14004671e  jmp     short loc_140046788
0x140046720  mov     rdx, cs:off_14001EA30; "Header"
0x140046727  jmp     short loc_140046752
0x140046729  lea     rdx, [rbp+57h+Handle]; void **
0x14004672d  call    ?VmxpOpenKsrKey@@YAJEPEAPEAX@Z; VmxpOpenKsrKey(uchar,void * *)
0x140046732  mov     ebx, eax
0x140046734  test    eax, eax
0x140046736  jns     short loc_14004673F
0x140046738  mov     esi, 2
0x14004673d  jmp     short loc_140046788
0x14004673f  mov     rdx, cs:off_14001EA38; "Toc"
0x140046746  cmp     rdi, 11h
0x14004674a  cmovz   rdx, cs:off_14001EA40; unsigned __int16 *
0x140046752  mov     rcx, [rbp+57h+Handle]; void *
0x140046756  lea     r9, [rbp+57h+var_C0]; unsigned int *
0x14004675a  imul    r14d, r13d
0x14004675e  lea     r8, [rbp+57h+P]; void **
0x140046762  mov     [rbp+57h+var_C0], r14d
0x140046766  call    ?VmxpGetDeviceParameterBinary@@YAJPEAXPEAGPEAPEAXPEAK@Z; VmxpGetDeviceParameterBinary(void *,ushort *,void * *,ulong *)
0x14004676b  mov     ebx, eax
0x14004676d  test    eax, eax
0x14004676f  jns     short loc_14004677C
0x140046771  mov     r12d, 4
0x140046777  mov     esi, r12d
0x14004677a  jmp     short loc_14004678E
0x14004677c  mov     rax, [rbp+57h+P]
0x140046780  mov     [r12], rax
0x140046784  mov     [rbp+57h+P], rsi
0x140046788  mov     r12d, 4
0x14004678e  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140046795  cmp     byte ptr [rax+130h], 0
0x14004679c  jz      loc_140046856
0x1400467a2  test    ebx, ebx
0x1400467a4  jns     loc_140046856
0x1400467aa  mov     rcx, [r15+10h]
0x1400467ae  lea     rdx, [rbp+57h+DstBuf]; DstBuf
0x1400467b2  mov     r15d, 10h
0x1400467b8  mov     r9d, r15d; Radix
0x1400467bb  mov     ecx, [rcx+20h]; Val
0x1400467be  lea     r14d, [r15-7]
0x1400467c2  mov     r8d, r14d; SizeInWords
0x1400467c5  call    cs:__imp__ultow_s
0x1400467cc  nop     dword ptr [rax+rax+00h]
0x1400467d1  mov     r9d, r15d; Radix
0x1400467d4  lea     r8d, [r15+1]; SizeInWords
0x1400467d8  lea     rdx, [rbp+57h+var_70]; DstBuf
0x1400467dc  mov     rcx, rdi; Val
0x1400467df  call    cs:__imp__ui64tow_s
0x1400467e6  nop     dword ptr [rax+rax+00h]
0x1400467eb  mov     r9d, r15d; Radix
0x1400467ee  lea     r8d, [r15-0Eh]; SizeInWords
0x1400467f2  lea     rdx, [rbp+57h+var_A8]; DstBuf
0x1400467f6  mov     ecx, esi; Val
0x1400467f8  call    cs:__imp__ultow_s
0x1400467ff  nop     dword ptr [rax+rax+00h]
0x140046804  mov     r9d, r15d; Radix
0x140046807  lea     rdx, [rbp+57h+var_A0]; DstBuf
0x14004680b  mov     r8d, r14d; SizeInWords
0x14004680e  mov     ecx, ebx; Val
0x140046810  call    cs:__imp__ultow_s
0x140046817  nop     dword ptr [rax+rax+00h]
0x14004681c  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140046823  lea     rcx, [rbp+57h+var_A0]
0x140046827  mov     [rsp+100h+var_D0], rcx
0x14004682c  lea     r9, [rbp+57h+DstBuf]
0x140046830  lea     rcx, [rbp+57h+var_A8]
0x140046834  movzx   r8d, r12w
0x140046838  mov     [rsp+100h+var_D8], rcx
0x14004683d  mov     edx, 80380002h
0x140046842  mov     rax, [rax+10h]
0x140046846  lea     rcx, [rbp+57h+var_70]
0x14004684a  mov     [rsp+100h+var_E0], rcx
0x14004684f  xor     ecx, ecx
0x140046851  call    _guard_dispatch_icall
0x140046856  mov     rcx, [rbp+57h+P]; P
0x14004685a  test    rcx, rcx
0x14004685d  jz      short loc_14004686D
0x14004685f  xor     edx, edx; Tag
0x140046861  call    cs:__imp_ExFreePoolWithTag
0x140046868  nop     dword ptr [rax+rax+00h]
0x14004686d  mov     rcx, [rbp+57h+Handle]; Handle
0x140046871  test    rcx, rcx
0x140046874  jz      short loc_140046882
0x140046876  call    cs:__imp_ZwClose
0x14004687d  nop     dword ptr [rax+rax+00h]
0x140046882  mov     eax, ebx
0x140046884  mov     rcx, [rbp+57h+var_48]
0x140046888  xor     rcx, rsp; StackCookie
0x14004688b  call    __security_check_cookie
0x140046890  add     rsp, 0C8h
0x140046897  pop     r15
0x140046899  pop     r14
0x14004689b  pop     r13
0x14004689d  pop     r12
0x14004689f  pop     rdi
0x1400468a0  pop     rsi
0x1400468a1  pop     rbx
0x1400468a2  pop     rbp
0x1400468a3  retn
```
