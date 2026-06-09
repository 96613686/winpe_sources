# VirtualDeviceRepository::ReadArray(ushort const *,uchar *,uint)

- ea: `0x1400f0490`
- end: `0x1400f06cb`
- name: `?ReadArray@VirtualDeviceRepository@@UEAAJPEBGPEAEI@Z`
- size: `571`
- prototype: `int(VirtualDeviceRepository *__hidden this, const unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1400364a0`
- `0x1400544a8`
- `0x140078628`
- `0x140083990`
- `0x14008a328`
- `0x1400f0490`
- `0x1400f06d4`
- `0x14011ea40`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400f05ab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400f05ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400f0661`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400f0661`

## string_xrefs

- `0x1400f05c7`: `onecore\vm\common\vml\VmMemory.h`
- `0x1400f04d4`: `onecore\vm\common\repository\core\virtualdevicerepository.cpp`
- `0x1400f0534`: `onecore\vm\common\repository\core\virtualdevicerepository.cpp`
- `0x1400f055c`: `onecore\vm\common\repository\core\virtualdevicerepository.cpp`
- `0x1400f0591`: `onecore\vm\common\repository\core\virtualdevicerepository.cpp`
- `0x1400f0606`: `onecore\vm\common\repository\core\virtualdevicerepository.cpp`
- `0x1400f064c`: `onecore\vm\common\repository\core\virtualdevicerepository.cpp`
- `0x1400f06b8`: `onecore\vm\common\repository\core\virtualdevicerepository.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VirtualDeviceRepository::ReadArray(
        VirtualDeviceRepository *this,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int a4)
{
  char *v8; // rsi
  int Access; // eax
  int v10; // eax
  HLOCAL v11; // rax
  const char *v12; // r9
  void *v13; // rbx
  int v14; // eax
  int v15; // eax
  const char *v16; // r9
  __int64 result; // rax
  int v18; // eax
  int v19; // [rsp+20h] [rbp-68h]
  int v20; // [rsp+20h] [rbp-68h]
  SIZE_T uBytes; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v8 = (char *)this - 24;
  Access = VirtualDeviceRepository::VerifyReadAccess((VirtualDeviceRepository *)((char *)this - 24), a2);
  try
  {
    if ( Access < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x736,
        (unsigned int)"onecore\\vm\\common\\repository\\core\\virtualdevicerepository.cpp",
        (const char *)(unsigned int)Access,
        v19);
    if ( *((_DWORD *)this + 33) )
    {
      LODWORD(uBytes) = 0;
      v10 = (*(__int64 (__fastcall **)(VirtualDeviceRepository *, const unsigned __int16 *, SIZE_T *))(*(_QWORD *)this + 288LL))(
              this,
              a2,
              &uBytes);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x742,
          (unsigned int)"onecore\\vm\\common\\repository\\core\\virtualdevicerepository.cpp",
          (const char *)(unsigned int)v10,
          v19);
      if ( a4 > (unsigned int)uBytes )
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x74A,
          (unsigned int)"onecore\\vm\\common\\repository\\core\\virtualdevicerepository.cpp",
          (const char *)0x8000FFFFLL,
          v19);
        if ( (unsigned int)VmlIsDebugTraceEnabled(0) )
          VmlDebugTraceEx(0, &off_1402E3DD0);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x74C,
          (unsigned int)"onecore\\vm\\common\\repository\\core\\virtualdevicerepository.cpp",
          (const char *)0x8000FFFFLL,
          v20);
      }
      v11 = LocalAlloc(0x40u, (unsigned int)uBytes);
      v13 = v11;
      if ( !v11 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x355,
          (unsigned int)"onecore\\vm\\common\\vml\\VmMemory.h",
          v12);
      v14 = (*(__int64 (__fastcall **)(char *, const unsigned __int16 *, HLOCAL, _QWORD))(*(_QWORD *)v8 + 64LL))(
              v8,
              a2,
              v11,
              (unsigned int)uBytes);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x753,
          (unsigned int)"onecore\\vm\\common\\repository\\core\\virtualdevicerepository.cpp",
          (const char *)(unsigned int)v14,
          v19);
      v15 = (*(__int64 (__fastcall **)(_QWORD, void *, _QWORD, unsigned __int8 *))(**((_QWORD **)this + 17) + 216LL))(
              *((_QWORD *)this + 17),
              v13,
              (unsigned int)uBytes,
              a3);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x759,
          (unsigned int)"onecore\\vm\\common\\repository\\core\\virtualdevicerepository.cpp",
          (const char *)(unsigned int)v15,
          a4);
      LocalFree(v13);
    }
    else
    {
      v18 = (*(__int64 (__fastcall **)(char *, const unsigned __int16 *, unsigned __int8 *, _QWORD))(*(_QWORD *)v8 + 64LL))(
              v8,
              a2,
              a3,
              a4);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x75F,
          (unsigned int)"onecore\\vm\\common\\repository\\core\\virtualdevicerepository.cpp",
          (const char *)(unsigned int)v18,
          v19);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x764,
                           (unsigned int)"onecore\\vm\\common\\repository\\core\\virtualdevicerepository.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x1400f0490  push    rbx
0x1400f0492  push    rsi
0x1400f0493  push    rdi
0x1400f0494  push    r12
0x1400f0496  push    r14
0x1400f0498  push    r15
0x1400f049a  sub     rsp, 58h
0x1400f049e  mov     rax, cs:__security_cookie
0x1400f04a5  xor     rax, rsp
0x1400f04a8  mov     [rsp+88h+var_40], rax
0x1400f04ad  mov     r15d, r9d
0x1400f04b0  mov     r12, r8
0x1400f04b3  mov     r14, rdx
0x1400f04b6  mov     rdi, rcx
0x1400f04b9  lea     rsi, [rcx-18h]
0x1400f04bd  mov     rcx, rsi; this
0x1400f04c0  call    ?VerifyReadAccess@VirtualDeviceRepository@@AEAAJPEBG@Z; VirtualDeviceRepository::VerifyReadAccess(ushort const *)
0x1400f04c5  mov     rcx, [rsp+88h]; this
0x1400f04cd  test    eax, eax
0x1400f04cf  jns     short loc_1400F04E5
0x1400f04d1  mov     r9d, eax; char *
0x1400f04d4  lea     r8, aOnecoreVmCommo_97; "onecore\\vm\\common\\repository\\core\\"...
0x1400f04db  mov     edx, 736h; void *
0x1400f04e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400f04e5  cmp     dword ptr [rdi+84h], 0
0x1400f04ec  jz      loc_1400F0691
0x1400f04f2  xorps   xmm0, xmm0
0x1400f04f5  movups  [rsp+88h+var_58], xmm0
0x1400f04fa  mov     qword ptr [rsp+88h+var_58], 0
0x1400f0503  mov     dword ptr [rsp+88h+uBytes], 0
0x1400f050b  mov     rax, [rdi]
0x1400f050e  lea     r8, [rsp+88h+uBytes]
0x1400f0513  mov     rdx, r14
0x1400f0516  mov     rcx, rdi
0x1400f0519  mov     rax, [rax+120h]
0x1400f0520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f0525  mov     rcx, [rsp+88h]; this
0x1400f052d  test    eax, eax
0x1400f052f  jns     short loc_1400F0545
0x1400f0531  mov     r9d, eax; char *
0x1400f0534  lea     r8, aOnecoreVmCommo_97; "onecore\\vm\\common\\repository\\core\\"...
0x1400f053b  mov     edx, 742h; void *
0x1400f0540  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400f0545  cmp     r15d, dword ptr [rsp+88h+uBytes]
0x1400f054a  jbe     short loc_1400F05A2
0x1400f054c  mov     rcx, [rsp+88h]; this
0x1400f0554  mov     ebx, 8000FFFFh
0x1400f0559  mov     r9d, ebx; char *
0x1400f055c  lea     r8, aOnecoreVmCommo_97; "onecore\\vm\\common\\repository\\core\\"...
0x1400f0563  mov     edx, 74Ah; void *
0x1400f0568  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1400f056d  xor     ecx, ecx
0x1400f056f  call    VmlIsDebugTraceEnabled
0x1400f0574  test    eax, eax
0x1400f0576  jz      short loc_1400F0586
0x1400f0578  lea     rdx, off_1402E3DD0; "Unexpected error.\n"
0x1400f057f  xor     ecx, ecx
0x1400f0581  call    VmlDebugTraceEx
0x1400f0586  mov     rcx, [rsp+88h]; this
0x1400f058e  mov     r9d, ebx; char *
0x1400f0591  lea     r8, aOnecoreVmCommo_97; "onecore\\vm\\common\\repository\\core\\"...
0x1400f0598  mov     edx, 74Ch; void *
0x1400f059d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400f05a2  mov     edx, dword ptr [rsp+88h+uBytes]; uBytes
0x1400f05a6  mov     ecx, 40h ; '@'; uFlags
0x1400f05ab  call    cs:__imp_LocalAlloc
0x1400f05b2  nop     dword ptr [rax+rax+00h]
0x1400f05b7  mov     rbx, rax
0x1400f05ba  test    rax, rax
0x1400f05bd  jnz     short loc_1400F05D8
0x1400f05bf  mov     rcx, [rsp+88h]; this
0x1400f05c7  lea     r8, aOnecoreVmCommo_35; "onecore\\vm\\common\\vml\\VmMemory.h"
0x1400f05ce  mov     edx, 355h; void *
0x1400f05d3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400f05d8  mov     qword ptr [rsp+88h+var_58], rbx
0x1400f05dd  mov     rax, [rsi]
0x1400f05e0  mov     r9d, dword ptr [rsp+88h+uBytes]
0x1400f05e5  mov     r8, rbx
0x1400f05e8  mov     rdx, r14
0x1400f05eb  mov     rcx, rsi
0x1400f05ee  mov     rax, [rax+40h]
0x1400f05f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f05f7  mov     rcx, [rsp+88h]; this
0x1400f05ff  test    eax, eax
0x1400f0601  jns     short loc_1400F0617
0x1400f0603  mov     r9d, eax; char *
0x1400f0606  lea     r8, aOnecoreVmCommo_97; "onecore\\vm\\common\\repository\\core\\"...
0x1400f060d  mov     edx, 753h; void *
0x1400f0612  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400f0617  mov     rcx, [rdi+88h]
0x1400f061e  mov     rax, [rcx]
0x1400f0621  mov     [rsp+88h+var_68], r15d; int
0x1400f0626  mov     r9, r12
0x1400f0629  mov     r8d, dword ptr [rsp+88h+uBytes]
0x1400f062e  mov     rdx, rbx
0x1400f0631  mov     rax, [rax+0D8h]
0x1400f0638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f063d  mov     rcx, [rsp+88h]; this
0x1400f0645  test    eax, eax
0x1400f0647  jns     short loc_1400F065E
0x1400f0649  mov     r9d, eax; char *
0x1400f064c  lea     r8, aOnecoreVmCommo_97; "onecore\\vm\\common\\repository\\core\\"...
0x1400f0653  mov     edx, 759h; void *
0x1400f0658  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400f065e  mov     rcx, rbx; hMem
0x1400f0661  call    cs:__imp_LocalFree
0x1400f0668  nop     dword ptr [rax+rax+00h]
0x1400f066d  xor     eax, eax
0x1400f066f  jmp     short loc_1400F0675
0x1400f0671  mov     eax, dword ptr [rsp+88h+uBytes]
0x1400f0675  mov     rcx, [rsp+88h+var_40]
0x1400f067a  xor     rcx, rsp; StackCookie
0x1400f067d  call    __security_check_cookie
0x1400f0682  add     rsp, 58h
0x1400f0686  pop     r15
0x1400f0688  pop     r14
0x1400f068a  pop     r12
0x1400f068c  pop     rdi
0x1400f068d  pop     rsi
0x1400f068e  pop     rbx
0x1400f068f  retn
0x1400f0691  mov     rax, [rsi]
0x1400f0694  mov     r9d, r15d
0x1400f0697  mov     r8, r12
0x1400f069a  mov     rdx, r14
0x1400f069d  mov     rcx, rsi
0x1400f06a0  mov     rax, [rax+40h]
0x1400f06a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f06a9  mov     rcx, [rsp+88h]; this
0x1400f06b1  test    eax, eax
0x1400f06b3  jns     short loc_1400F066D
0x1400f06b5  mov     r9d, eax; char *
0x1400f06b8  lea     r8, aOnecoreVmCommo_97; "onecore\\vm\\common\\repository\\core\\"...
0x1400f06bf  mov     edx, 75Fh; void *
0x1400f06c4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
