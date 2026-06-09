# VirtualDeviceRepository::ReadArray(ushort const *,uchar *,uint)

- ea: `0x140102020`
- end: `0x14010225b`
- name: `?ReadArray@VirtualDeviceRepository@@UEAAJPEBGPEAEI@Z`
- size: `571`
- prototype: `int(VirtualDeviceRepository *__hidden this, const unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140042260`
- `0x14005497c`
- `0x14005b648`
- `0x14006af58`
- `0x140078cb8`
- `0x140102020`
- `0x140102264`
- `0x140132960`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1401021f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1401021f1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14010213b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14010213b`

## string_xrefs

- `0x140102157`: `onecore\vm\common\vml\VmMemory.h`
- `0x140102064`: `onecore\vm\common\repository\core\virtualdevicerepository.cpp`
- `0x1401020c4`: `onecore\vm\common\repository\core\virtualdevicerepository.cpp`
- `0x1401020ec`: `onecore\vm\common\repository\core\virtualdevicerepository.cpp`
- `0x140102121`: `onecore\vm\common\repository\core\virtualdevicerepository.cpp`
- `0x140102196`: `onecore\vm\common\repository\core\virtualdevicerepository.cpp`
- `0x1401021dc`: `onecore\vm\common\repository\core\virtualdevicerepository.cpp`
- `0x140102248`: `onecore\vm\common\repository\core\virtualdevicerepository.cpp`

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
          VmlDebugTraceEx(0, &off_1402DA9A8);
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
0x140102020  push    rbx
0x140102022  push    rsi
0x140102023  push    rdi
0x140102024  push    r12
0x140102026  push    r14
0x140102028  push    r15
0x14010202a  sub     rsp, 58h
0x14010202e  mov     rax, cs:__security_cookie
0x140102035  xor     rax, rsp
0x140102038  mov     [rsp+88h+var_40], rax
0x14010203d  mov     r15d, r9d
0x140102040  mov     r12, r8
0x140102043  mov     r14, rdx
0x140102046  mov     rdi, rcx
0x140102049  lea     rsi, [rcx-18h]
0x14010204d  mov     rcx, rsi; this
0x140102050  call    ?VerifyReadAccess@VirtualDeviceRepository@@AEAAJPEBG@Z; VirtualDeviceRepository::VerifyReadAccess(ushort const *)
0x140102055  mov     rcx, [rsp+88h]; this
0x14010205d  test    eax, eax
0x14010205f  jns     short loc_140102075
0x140102061  mov     r9d, eax; char *
0x140102064  lea     r8, aOnecoreVmCommo_97; "onecore\\vm\\common\\repository\\core\\"...
0x14010206b  mov     edx, 736h; void *
0x140102070  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140102075  cmp     dword ptr [rdi+84h], 0
0x14010207c  jz      loc_140102221
0x140102082  xorps   xmm0, xmm0
0x140102085  movups  [rsp+88h+var_58], xmm0
0x14010208a  mov     qword ptr [rsp+88h+var_58], 0
0x140102093  mov     dword ptr [rsp+88h+uBytes], 0
0x14010209b  mov     rax, [rdi]
0x14010209e  lea     r8, [rsp+88h+uBytes]
0x1401020a3  mov     rdx, r14
0x1401020a6  mov     rcx, rdi
0x1401020a9  mov     rax, [rax+120h]
0x1401020b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401020b5  mov     rcx, [rsp+88h]; this
0x1401020bd  test    eax, eax
0x1401020bf  jns     short loc_1401020D5
0x1401020c1  mov     r9d, eax; char *
0x1401020c4  lea     r8, aOnecoreVmCommo_97; "onecore\\vm\\common\\repository\\core\\"...
0x1401020cb  mov     edx, 742h; void *
0x1401020d0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1401020d5  cmp     r15d, dword ptr [rsp+88h+uBytes]
0x1401020da  jbe     short loc_140102132
0x1401020dc  mov     rcx, [rsp+88h]; this
0x1401020e4  mov     ebx, 8000FFFFh
0x1401020e9  mov     r9d, ebx; char *
0x1401020ec  lea     r8, aOnecoreVmCommo_97; "onecore\\vm\\common\\repository\\core\\"...
0x1401020f3  mov     edx, 74Ah; void *
0x1401020f8  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1401020fd  xor     ecx, ecx
0x1401020ff  call    VmlIsDebugTraceEnabled
0x140102104  test    eax, eax
0x140102106  jz      short loc_140102116
0x140102108  lea     rdx, off_1402DA9A8; "Unexpected error.\n"
0x14010210f  xor     ecx, ecx
0x140102111  call    VmlDebugTraceEx
0x140102116  mov     rcx, [rsp+88h]; this
0x14010211e  mov     r9d, ebx; char *
0x140102121  lea     r8, aOnecoreVmCommo_97; "onecore\\vm\\common\\repository\\core\\"...
0x140102128  mov     edx, 74Ch; void *
0x14010212d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140102132  mov     edx, dword ptr [rsp+88h+uBytes]; uBytes
0x140102136  mov     ecx, 40h ; '@'; uFlags
0x14010213b  call    cs:__imp_LocalAlloc
0x140102142  nop     dword ptr [rax+rax+00h]
0x140102147  mov     rbx, rax
0x14010214a  test    rax, rax
0x14010214d  jnz     short loc_140102168
0x14010214f  mov     rcx, [rsp+88h]; this
0x140102157  lea     r8, aOnecoreVmCommo_36; "onecore\\vm\\common\\vml\\VmMemory.h"
0x14010215e  mov     edx, 355h; void *
0x140102163  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140102168  mov     qword ptr [rsp+88h+var_58], rbx
0x14010216d  mov     rax, [rsi]
0x140102170  mov     r9d, dword ptr [rsp+88h+uBytes]
0x140102175  mov     r8, rbx
0x140102178  mov     rdx, r14
0x14010217b  mov     rcx, rsi
0x14010217e  mov     rax, [rax+40h]
0x140102182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140102187  mov     rcx, [rsp+88h]; this
0x14010218f  test    eax, eax
0x140102191  jns     short loc_1401021A7
0x140102193  mov     r9d, eax; char *
0x140102196  lea     r8, aOnecoreVmCommo_97; "onecore\\vm\\common\\repository\\core\\"...
0x14010219d  mov     edx, 753h; void *
0x1401021a2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1401021a7  mov     rcx, [rdi+88h]
0x1401021ae  mov     rax, [rcx]
0x1401021b1  mov     [rsp+88h+var_68], r15d; int
0x1401021b6  mov     r9, r12
0x1401021b9  mov     r8d, dword ptr [rsp+88h+uBytes]
0x1401021be  mov     rdx, rbx
0x1401021c1  mov     rax, [rax+0D8h]
0x1401021c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401021cd  mov     rcx, [rsp+88h]; this
0x1401021d5  test    eax, eax
0x1401021d7  jns     short loc_1401021EE
0x1401021d9  mov     r9d, eax; char *
0x1401021dc  lea     r8, aOnecoreVmCommo_97; "onecore\\vm\\common\\repository\\core\\"...
0x1401021e3  mov     edx, 759h; void *
0x1401021e8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1401021ee  mov     rcx, rbx; hMem
0x1401021f1  call    cs:__imp_LocalFree
0x1401021f8  nop     dword ptr [rax+rax+00h]
0x1401021fd  xor     eax, eax
0x1401021ff  jmp     short loc_140102205
0x140102201  mov     eax, dword ptr [rsp+88h+uBytes]
0x140102205  mov     rcx, [rsp+88h+var_40]
0x14010220a  xor     rcx, rsp; StackCookie
0x14010220d  call    __security_check_cookie
0x140102212  add     rsp, 58h
0x140102216  pop     r15
0x140102218  pop     r14
0x14010221a  pop     r12
0x14010221c  pop     rdi
0x14010221d  pop     rsi
0x14010221e  pop     rbx
0x14010221f  retn
0x140102221  mov     rax, [rsi]
0x140102224  mov     r9d, r15d
0x140102227  mov     r8, r12
0x14010222a  mov     rdx, r14
0x14010222d  mov     rcx, rsi
0x140102230  mov     rax, [rax+40h]
0x140102234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140102239  mov     rcx, [rsp+88h]; this
0x140102241  test    eax, eax
0x140102243  jns     short loc_1401021FD
0x140102245  mov     r9d, eax; char *
0x140102248  lea     r8, aOnecoreVmCommo_97; "onecore\\vm\\common\\repository\\core\\"...
0x14010224f  mov     edx, 75Fh; void *
0x140102254  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
