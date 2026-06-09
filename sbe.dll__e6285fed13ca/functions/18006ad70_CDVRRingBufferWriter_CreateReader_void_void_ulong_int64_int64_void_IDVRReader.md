# CDVRRingBufferWriter::CreateReader(void (*)(void *,ulong,__int64,__int64),void *,IDVRReader * *)

- ea: `0x18006ad70`
- end: `0x18006b019`
- name: `?CreateReader@CDVRRingBufferWriter@@UEAAJP6AXPEAXK_J1@Z0PEAPEAUIDVRReader@@@Z`
- size: `681`
- prototype: `__int64 __fastcall(CDVRRingBufferWriter *__hidden this, void (*)(void *, unsigned int, __int64, __int64), void *, struct IDVRReader **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800017a0`
- `0x180001c00`
- `0x180063224`
- `0x18006ad70`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!DuplicateHandle` at `0x18006ae4b`
- `KERNEL32!DuplicateHandle` at `0x18006ae4b`
- `KERNEL32!GetLastError` at `0x18006ae57`
- `KERNEL32!GetLastError` at `0x18006ae57`
- `KERNEL32!GetCurrentProcess` at `0x18006ae0f`
- `KERNEL32!GetCurrentProcess` at `0x18006ae1c`
- `KERNEL32!GetCurrentProcess` at `0x18006ae0f`
- `KERNEL32!GetCurrentProcess` at `0x18006ae1c`
- `ADVAPI32!RegCloseKey` at `0x18006aff9`
- `ADVAPI32!RegCloseKey` at `0x18006b00c`
- `ADVAPI32!RegCloseKey` at `0x1800b4140`
- `ADVAPI32!RegCloseKey` at `0x1800b4153`
- `ADVAPI32!RegCloseKey` at `0x18006aff9`
- `ADVAPI32!RegCloseKey` at `0x18006b00c`
- `ADVAPI32!RegCloseKey` at `0x1800b4140`
- `ADVAPI32!RegCloseKey` at `0x1800b4153`
- `ADVAPI32!RegCreateKeyExW` at `0x18006aeb0`
- `ADVAPI32!RegCreateKeyExW` at `0x18006aeb0`

## string_xrefs

- `0x18006aea1`: `IO\Reader`

## pseudocode

```c
__int64 __fastcall CDVRRingBufferWriter::CreateReader(
        CDVRRingBufferWriter *this,
        void (*a2)(void *, unsigned int, __int64, __int64),
        void *a3,
        struct IDVRReader **a4)
{
  int v7; // esi
  CDVRReader *v8; // r14
  int v9; // r15d
  HANDLE CurrentProcess; // rbx
  void *v11; // rdi
  HANDLE v12; // rax
  int LastError; // eax
  CDVRReader *v14; // rcx
  int v15; // [rsp+80h] [rbp-78h] BYREF
  int v16; // [rsp+84h] [rbp-74h]
  CDVRReader *v17; // [rsp+88h] [rbp-70h]
  void *v18; // [rsp+90h] [rbp-68h]
  void (*v19)(void *, unsigned int, __int64, __int64); // [rsp+98h] [rbp-60h]
  HANDLE TargetHandle; // [rsp+A0h] [rbp-58h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp-50h] BYREF

  v18 = a3;
  v19 = a2;
  if ( !a4 )
    return 2147942487LL;
  v7 = 0;
  v15 = 0;
  v8 = 0;
  v17 = 0;
  hKey = 0;
  TargetHandle = 0;
  v9 = 1;
  v16 = 1;
  *a4 = 0;
  CurrentProcess = GetCurrentProcess();
  v11 = (void *)*((_QWORD *)this + 9);
  v12 = GetCurrentProcess();
  if ( DuplicateHandle(v12, v11, CurrentProcess, &TargetHandle, 0, 0, 2u) )
  {
    LastError = RegCreateKeyExW((HKEY)TargetHandle, L"IO\\Reader", 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
    if ( LastError )
    {
      if ( LastError <= 0 )
      {
        v7 = LastError;
        goto LABEL_6;
      }
      goto LABEL_5;
    }
    v14 = (CDVRReader *)operator new(0x1F8u);
    if ( v14 )
    {
      v8 = CDVRReader::CDVRReader(
             v14,
             *((struct CPVRIOCounters **)this + 20),
             *((struct CDVRFileCollection **)this + 72),
             *((_DWORD *)this + 150),
             *((void ***)this + 76),
             *((_DWORD *)this + 16),
             *((struct CAsyncIo **)this + 16),
             *((_DWORD *)this + 34),
             *((_DWORD *)this + 35),
             v19,
             v18,
             (HKEY)TargetHandle,
             hKey,
             *((_DWORD *)this + 38),
             &v15);
      v7 = v15;
    }
    else
    {
      v8 = 0;
    }
    v17 = v8;
    if ( v8 )
    {
      v9 = 0;
      v16 = 0;
      if ( v7 >= 0 )
      {
        v7 = (**(__int64 (__fastcall ***)(CDVRReader *, GUID *, struct IDVRReader **))v8)(v8, &IID_IDVRReader, a4);
        v15 = v7;
      }
      goto LABEL_17;
    }
    v7 = -2147024882;
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
LABEL_5:
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_6:
  v15 = v7;
LABEL_17:
  if ( v7 < 0 )
  {
    if ( v8 )
      (*(void (__fastcall **)(CDVRReader *, __int64))(*(_QWORD *)v8 + 136LL))(v8, 1);
    if ( v9 )
    {
      if ( hKey )
        RegCloseKey(hKey);
      if ( TargetHandle )
        RegCloseKey((HKEY)TargetHandle);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18006ad70  push    rbx
0x18006ad72  push    rsi
0x18006ad73  push    rdi
0x18006ad74  push    r12
0x18006ad76  push    r13
0x18006ad78  push    r14
0x18006ad7a  push    r15
0x18006ad7c  sub     rsp, 0C0h
0x18006ad83  mov     rax, cs:__security_cookie
0x18006ad8a  xor     rax, rsp
0x18006ad8d  mov     [rsp+0F8h+var_48], rax
0x18006ad95  mov     r12, r9
0x18006ad98  mov     [rsp+0F8h+var_68], r8
0x18006ada0  mov     [rsp+0F8h+var_60], rdx
0x18006ada8  mov     r13, rcx
0x18006adab  xor     eax, eax
0x18006adad  test    r9, r9
0x18006adb0  jnz     short loc_18006ADDA
0x18006adb2  mov     eax, 80070057h
0x18006adb7  mov     rcx, [rsp+0F8h+var_48]
0x18006adbf  xor     rcx, rsp; StackCookie
0x18006adc2  call    __security_check_cookie
0x18006adc7  add     rsp, 0C0h
0x18006adce  pop     r15
0x18006add0  pop     r14
0x18006add2  pop     r13
0x18006add4  pop     r12
0x18006add6  pop     rdi
0x18006add7  pop     rsi
0x18006add8  pop     rbx
0x18006add9  retn
0x18006adda  mov     esi, eax
0x18006addc  mov     [rsp+0F8h+var_78], eax
0x18006ade3  mov     r14, rax
0x18006ade6  mov     [rsp+0F8h+var_70], rax
0x18006adee  mov     [rsp+0F8h+hKey], rax
0x18006adf6  mov     [rsp+0F8h+TargetHandle], rax
0x18006adfe  mov     r15d, 1
0x18006ae04  mov     [rsp+0F8h+var_74], r15d
0x18006ae0c  mov     [r9], rax
0x18006ae0f  call    cs:__imp_GetCurrentProcess
0x18006ae15  mov     rbx, rax
0x18006ae18  mov     rdi, [r13+48h]
0x18006ae1c  call    cs:__imp_GetCurrentProcess
0x18006ae22  mov     [rsp+0F8h+dwOptions], 2; dwOptions
0x18006ae2a  mov     [rsp+0F8h+bInheritHandle], 0; bInheritHandle
0x18006ae32  mov     [rsp+0F8h+dwDesiredAccess], 0; dwDesiredAccess
0x18006ae3a  lea     r9, [rsp+0F8h+TargetHandle]; lpTargetHandle
0x18006ae42  mov     r8, rbx; hTargetProcessHandle
0x18006ae45  mov     rdx, rdi; hSourceHandle
0x18006ae48  mov     rcx, rax; hSourceProcessHandle
0x18006ae4b  call    cs:__imp_DuplicateHandle
0x18006ae51  xor     ebx, ebx
0x18006ae53  test    eax, eax
0x18006ae55  jnz     short loc_18006AE78
0x18006ae57  call    cs:__imp_GetLastError
0x18006ae5d  mov     esi, eax
0x18006ae5f  test    eax, eax
0x18006ae61  jle     short loc_18006AE6C
0x18006ae63  movzx   esi, ax
0x18006ae66  or      esi, 80070000h
0x18006ae6c  mov     [rsp+0F8h+var_78], esi
0x18006ae73  jmp     loc_18006AFC7
0x18006ae78  mov     [rsp+0F8h+lpdwDisposition], rbx; lpdwDisposition
0x18006ae7d  lea     rax, [rsp+0F8h+hKey]
0x18006ae85  mov     [rsp+0F8h+phkResult], rax; phkResult
0x18006ae8a  mov     qword ptr [rsp+0F8h+dwOptions], rbx; lpSecurityAttributes
0x18006ae8f  mov     [rsp+0F8h+bInheritHandle], 2001Fh; samDesired
0x18006ae97  mov     [rsp+0F8h+dwDesiredAccess], ebx; dwOptions
0x18006ae9b  xor     r9d, r9d; lpClass
0x18006ae9e  xor     r8d, r8d; Reserved
0x18006aea1  lea     rdx, aIoReader; "IO\\Reader"
0x18006aea8  mov     rcx, [rsp+0F8h+TargetHandle]; hKey
0x18006aeb0  call    cs:__imp_RegCreateKeyExW
0x18006aeb6  test    eax, eax
0x18006aeb8  jz      short loc_18006AEC0
0x18006aeba  jg      short loc_18006AE63
0x18006aebc  mov     esi, eax
0x18006aebe  jmp     short loc_18006AE6C
0x18006aec0  mov     ecx, 1F8h; Size
0x18006aec5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006aeca  mov     rcx, rax; this
0x18006aecd  test    rax, rax
0x18006aed0  jz      loc_18006AF7E
0x18006aed6  lea     rax, [rsp+0F8h+var_78]
0x18006aede  mov     [rsp+0F8h+var_88], rax; int *
0x18006aee3  mov     eax, [r13+98h]
0x18006aeea  mov     [rsp+0F8h+var_90], eax; int
0x18006aeee  mov     rax, [rsp+0F8h+hKey]
0x18006aef6  mov     [rsp+0F8h+var_98], rax; HKEY
0x18006aefb  mov     rax, [rsp+0F8h+TargetHandle]
0x18006af03  mov     [rsp+0F8h+var_A0], rax; HKEY
0x18006af08  mov     rax, [rsp+0F8h+var_68]
0x18006af10  mov     [rsp+0F8h+var_A8], rax; void *
0x18006af15  mov     rax, [rsp+0F8h+var_60]
0x18006af1d  mov     [rsp+0F8h+var_B0], rax; void (*)(void *, unsigned int, __int64, __int64)
0x18006af22  mov     eax, [r13+8Ch]
0x18006af29  mov     dword ptr [rsp+0F8h+lpdwDisposition], eax; unsigned int
0x18006af2d  mov     eax, [r13+88h]
0x18006af34  mov     dword ptr [rsp+0F8h+phkResult], eax; unsigned int
0x18006af38  mov     rax, [r13+80h]
0x18006af3f  mov     qword ptr [rsp+0F8h+dwOptions], rax; struct CAsyncIo *
0x18006af44  mov     eax, [r13+40h]
0x18006af48  mov     [rsp+0F8h+bInheritHandle], eax; unsigned int
0x18006af4c  mov     rax, [r13+260h]
0x18006af53  mov     qword ptr [rsp+0F8h+dwDesiredAccess], rax; void **
0x18006af58  mov     r9d, [r13+258h]; unsigned int
0x18006af5f  mov     r8, [r13+240h]; struct CDVRFileCollection *
0x18006af66  mov     rdx, [r13+0A0h]; struct CPVRIOCounters *
0x18006af6d  call    ??0CDVRReader@@QEAA@PEAVCPVRIOCounters@@PEAVCDVRFileCollection@@KPEAPEAXKPEAVCAsyncIo@@KKP6AXPEAXK_J5@Z4PEAUHKEY__@@7HPEAJ@Z; CDVRReader::CDVRReader(CPVRIOCounters *,CDVRFileCollection *,ulong,void * *,ulong,CAsyncIo *,ulong,ulong,void (*)(void *,ulong,__int64,__int64),void *,HKEY__ *,HKEY__ *,int,long *)
0x18006af72  mov     r14, rax
0x18006af75  mov     esi, [rsp+0F8h+var_78]
0x18006af7c  jmp     short loc_18006AF81
0x18006af7e  mov     r14, rbx
0x18006af81  mov     [rsp+0F8h+var_70], r14
0x18006af89  test    r14, r14
0x18006af8c  jnz     short loc_18006AF98
0x18006af8e  mov     esi, 8007000Eh
0x18006af93  jmp     loc_18006AE6C
0x18006af98  mov     r15d, ebx
0x18006af9b  mov     [rsp+0F8h+var_74], ebx
0x18006afa2  test    esi, esi
0x18006afa4  js      short loc_18006AFC7
0x18006afa6  mov     rax, [r14]
0x18006afa9  mov     r8, r12
0x18006afac  lea     rdx, IID_IDVRReader
0x18006afb3  mov     rcx, r14
0x18006afb6  mov     rax, [rax]
0x18006afb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006afbe  mov     esi, eax
0x18006afc0  mov     [rsp+0F8h+var_78], eax
0x18006afc7  test    esi, esi
0x18006afc9  jns     short loc_18006B012
0x18006afcb  test    r14, r14
0x18006afce  jz      short loc_18006AFE7
0x18006afd0  mov     rax, [r14]
0x18006afd3  mov     edx, 1
0x18006afd8  mov     rcx, r14
0x18006afdb  mov     rax, [rax+88h]
0x18006afe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006afe7  test    r15d, r15d
0x18006afea  jz      short loc_18006B012
0x18006afec  mov     rcx, [rsp+0F8h+hKey]; hKey
0x18006aff4  test    rcx, rcx
0x18006aff7  jz      short loc_18006AFFF
0x18006aff9  call    cs:__imp_RegCloseKey
0x18006afff  mov     rcx, [rsp+0F8h+TargetHandle]; hKey
0x18006b007  test    rcx, rcx
0x18006b00a  jz      short loc_18006B012
0x18006b00c  call    cs:__imp_RegCloseKey
0x18006b012  mov     eax, esi
0x18006b014  jmp     loc_18006ADB7
0x1800b40f5  push    rbp
0x1800b40f7  sub     rsp, 80h
0x1800b40fe  mov     rbp, rdx
0x1800b4101  cmp     dword ptr [rbp+80h], 0
0x1800b4108  jge     short loc_1800B415A
0x1800b410a  mov     rcx, [rbp+88h]
0x1800b4111  test    rcx, rcx
0x1800b4114  jz      short loc_1800B412B
0x1800b4116  mov     rax, [rcx]
0x1800b4119  mov     edx, 1
0x1800b411e  mov     rax, [rax+88h]
0x1800b4125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b412a  nop
0x1800b412b  cmp     dword ptr [rbp+84h], 0
0x1800b4132  jz      short loc_1800B415A
0x1800b4134  mov     rcx, [rbp+0A8h]; hKey
0x1800b413b  test    rcx, rcx
0x1800b413e  jz      short loc_1800B4147
0x1800b4140  call    cs:__imp_RegCloseKey
0x1800b4146  nop
0x1800b4147  mov     rcx, [rbp+0A0h]; hKey
0x1800b414e  test    rcx, rcx
0x1800b4151  jz      short loc_1800B415A
0x1800b4153  call    cs:__imp_RegCloseKey
0x1800b4159  nop
0x1800b415a  add     rsp, 80h
0x1800b4161  pop     rbp
0x1800b4162  retn
```
