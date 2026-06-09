# p9fs::Plan9VirtioDevice::MapDeviceMemory(unsigned __int64,unsigned __int64)

- ea: `0x18002de94`
- end: `0x18002e188`
- name: `?MapDeviceMemory@Plan9VirtioDevice@p9fs@@AEAA?AUDeviceMemory@12@_K0@Z`
- size: `756`
- prototype: `struct p9fs::Plan9VirtioDevice::DeviceMemory __high(unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002db40`

## callees

- `0x180004120`
- `0x18000456c`
- `0x1800167e0`
- `0x18002cc94`
- `0x18002cd54`
- `0x18002de94`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002df0a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002df0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002e162`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002e162`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002df66`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002df79`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002df66`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002df79`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002df8f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002df8f`
- `vmdevicehost!HdvCreateGuestMemoryAperture` at `0x18002e01a`
- `vmdevicehost!HdvCreateGuestMemoryAperture` at `0x18002e01a`

## string_xrefs

- `0x18002e045`: `onecore\vm\dv\storage\plan9\dll\windows\p9virtio.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall p9fs::Plan9VirtioDevice::MapDeviceMemory(RTL_SRWLOCK *a1, __int64 a2, char *a3, unsigned __int64 a4)
{
  RTL_SRWLOCK *v8; // rsi
  PVOID Ptr; // rcx
  char *v10; // rax
  PVOID v11; // rcx
  RTL_SRWLOCK *v12; // r15
  HRESULT v13; // eax
  _QWORD *v14; // rax
  _QWORD *v15; // r14
  PVOID v16; // r13
  PVOID v17; // r13
  PVOID v18; // rcx
  int v20; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int64 v21; // [rsp+48h] [rbp-50h] BYREF
  PVOID mappedAddress; // [rsp+50h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  mappedAddress = a3;
  v21 = a4;
  if ( a4 > 0x4000000 )
  {
    v20 = 0;
    Plan9TraceLoggingProvider::VirtIoAddressOutOfRange<int,unsigned __int64 &,unsigned __int64 &>(
      &v20,
      &mappedAddress,
      &v21);
LABEL_3:
    *(_OWORD *)(a2 + 8) = 0;
    *(_QWORD *)a2 = 0;
    return a2;
  }
  v8 = a1 + 19;
  AcquireSRWLockShared(a1 + 19);
  Ptr = a1[20].Ptr;
  if ( Ptr )
  {
    v10 = (char *)a1[21].Ptr;
    if ( a3 >= v10 && &a3[a4] <= v10 + 0x4000000 )
    {
      *(_QWORD *)a2 = Ptr;
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 8LL))(Ptr);
      *(RTL_SRWLOCK *)(a2 + 8) = a1[21];
      *(RTL_SRWLOCK *)(a2 + 16) = a1[22];
      if ( v8 )
        ReleaseSRWLockShared(v8);
      return a2;
    }
  }
  if ( v8 )
    ReleaseSRWLockShared(v8);
  if ( (unsigned __int64)a3 > 0xFFFFFFFFFC000000uLL )
    goto LABEL_3;
  AcquireSRWLockExclusive(v8);
  v11 = a1[20].Ptr;
  v12 = a1 + 21;
  if ( !v11 )
    goto LABEL_17;
  if ( a3 < v12->Ptr || &a3[a4] > (char *)v12->Ptr + 0x4000000 )
  {
    Plan9TraceLoggingProvider::VirtIoAddressOutOfRange<unsigned __int64 &,unsigned __int64 &,unsigned __int64 &>(
      &a1[21],
      &mappedAddress,
      &v21);
LABEL_17:
    mappedAddress = 0;
    v13 = HdvCreateGuestMemoryAperture(a1[4].Ptr, (UINT64)a3, 0x4000000u, 0, &mappedAddress);
    if ( v13 >= 0 )
    {
      v14 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
      v15 = v14;
      if ( v14 )
      {
        v16 = mappedAddress;
        *((_DWORD *)v14 + 3) = 1;
        *v14 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::`vftable';
        if ( Microsoft::WRL::Details::ModuleBase::module_ )
          (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                               + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
        *v15 = &p9fs::Plan9VirtioDevice::MemoryAperture::`vftable';
        v15[2] = a1;
        v15[3] = v16;
        v17 = a1[20].Ptr;
        a1[20].Ptr = v15;
        (*(void (__fastcall **)(_QWORD *))(*v15 + 8LL))(v15);
        if ( v17 )
          (*(void (__fastcall **)(PVOID))(*(_QWORD *)v17 + 16LL))(v17);
        v12->Ptr = a3;
        a1[22].Ptr = (PVOID)v15[3];
        v18 = a1[20].Ptr;
        *(_QWORD *)a2 = v18;
        if ( v18 )
          (*(void (__fastcall **)(PVOID))(*(_QWORD *)v18 + 8LL))(v18);
        *(RTL_SRWLOCK *)(a2 + 8) = a1[21];
        *(RTL_SRWLOCK *)(a2 + 16) = a1[22];
        (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
      }
      else
      {
        *(_OWORD *)(a2 + 8) = 0;
        *(_QWORD *)a2 = 0;
      }
    }
    else
    {
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x229,
        (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9virtio.cpp",
        (const char *)(unsigned int)v13,
        (int)"Mapping device memory failed, address %llu size %u",
        a3,
        0x4000000);
      *(_OWORD *)(a2 + 8) = 0;
      *(_QWORD *)a2 = 0;
    }
    goto LABEL_28;
  }
  *(_QWORD *)a2 = v11;
  (*(void (__fastcall **)(PVOID))(*(_QWORD *)v11 + 8LL))(v11);
  *(RTL_SRWLOCK *)(a2 + 8) = (RTL_SRWLOCK)v12->Ptr;
  *(RTL_SRWLOCK *)(a2 + 16) = a1[22];
LABEL_28:
  if ( v8 )
    ReleaseSRWLockExclusive(v8);
  return a2;
}

```

## disassembly

```asm
0x18002de94  mov     r11, rsp
0x18002de97  push    rbp
0x18002de98  push    rsi
0x18002de99  push    rdi
0x18002de9a  push    r12
0x18002de9c  push    r13
0x18002de9e  push    r14
0x18002dea0  push    r15
0x18002dea2  sub     rsp, 60h
0x18002dea6  mov     rax, cs:__security_cookie
0x18002dead  xor     rax, rsp
0x18002deb0  mov     [rsp+98h+var_40], rax
0x18002deb5  mov     r14, r9
0x18002deb8  mov     r12, r8
0x18002debb  mov     rdi, rdx
0x18002debe  mov     rbp, rcx
0x18002dec1  mov     [r11-48h], r8
0x18002dec5  mov     [r11-50h], r9
0x18002dec9  mov     r13d, 4000000h
0x18002decf  cmp     r9, r13
0x18002ded2  jbe     short loc_18002DF00
0x18002ded4  mov     [rsp+98h+var_58], 0
0x18002dedc  lea     r8, [r11-50h]
0x18002dee0  lea     rdx, [r11-48h]
0x18002dee4  lea     rcx, [r11-58h]
0x18002dee8  call    ??$VirtIoAddressOutOfRange@HAEA_KAEA_K@Plan9TraceLoggingProvider@@SAX$$QEAHAEA_K1@Z; Plan9TraceLoggingProvider::VirtIoAddressOutOfRange<int,unsigned __int64 &,unsigned __int64 &>(int &&,unsigned __int64 &,unsigned __int64 &)
0x18002deed  xorps   xmm0, xmm0
0x18002def0  movups  xmmword ptr [rdi+8], xmm0
0x18002def4  mov     qword ptr [rdi], 0
0x18002defb  jmp     loc_18002E168
0x18002df00  lea     rsi, [rcx+98h]
0x18002df07  mov     rcx, rsi; SRWLock
0x18002df0a  call    cs:__imp_AcquireSRWLockShared
0x18002df10  mov     rcx, [rbp+0A0h]
0x18002df17  test    rcx, rcx
0x18002df1a  jz      short loc_18002DF71
0x18002df1c  mov     rax, [rbp+0A8h]
0x18002df23  cmp     r12, rax
0x18002df26  jb      short loc_18002DF71
0x18002df28  lea     rdx, [r14+r12]
0x18002df2c  add     rax, r13
0x18002df2f  cmp     rdx, rax
0x18002df32  ja      short loc_18002DF71
0x18002df34  mov     [rdi], rcx
0x18002df37  mov     rax, [rcx]
0x18002df3a  mov     rax, [rax+8]
0x18002df3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df43  nop
0x18002df44  mov     rax, [rbp+0A8h]
0x18002df4b  mov     [rdi+8], rax
0x18002df4f  mov     rax, [rbp+0B0h]
0x18002df56  mov     [rdi+10h], rax
0x18002df5a  test    rsi, rsi
0x18002df5d  jz      loc_18002E168
0x18002df63  mov     rcx, rsi; SRWLock
0x18002df66  call    cs:__imp_ReleaseSRWLockShared
0x18002df6c  jmp     loc_18002E168
0x18002df71  test    rsi, rsi
0x18002df74  jz      short loc_18002DF7F
0x18002df76  mov     rcx, rsi; SRWLock
0x18002df79  call    cs:__imp_ReleaseSRWLockShared
0x18002df7f  cmp     r12, 0FFFFFFFFFC000000h
0x18002df86  ja      loc_18002DEED
0x18002df8c  mov     rcx, rsi; SRWLock
0x18002df8f  call    cs:__imp_AcquireSRWLockExclusive
0x18002df95  mov     rcx, [rbp+0A0h]
0x18002df9c  lea     r15, [rbp+0A8h]
0x18002dfa3  test    rcx, rcx
0x18002dfa6  jz      short loc_18002DFFA
0x18002dfa8  mov     rax, [r15]
0x18002dfab  cmp     r12, rax
0x18002dfae  jb      short loc_18002DFE3
0x18002dfb0  lea     rdx, [r14+r12]
0x18002dfb4  add     rax, r13
0x18002dfb7  cmp     rdx, rax
0x18002dfba  ja      short loc_18002DFE3
0x18002dfbc  mov     [rdi], rcx
0x18002dfbf  mov     rax, [rcx]
0x18002dfc2  mov     rax, [rax+8]
0x18002dfc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfcb  nop
0x18002dfcc  mov     rax, [r15]
0x18002dfcf  mov     [rdi+8], rax
0x18002dfd3  mov     rax, [rbp+0B0h]
0x18002dfda  mov     [rdi+10h], rax
0x18002dfde  jmp     loc_18002E15A
0x18002dfe3  test    rcx, rcx
0x18002dfe6  jz      short loc_18002DFFA
0x18002dfe8  lea     r8, [rsp+98h+var_50]
0x18002dfed  lea     rdx, [rsp+98h+var_48]
0x18002dff2  mov     rcx, r15
0x18002dff5  call    ??$VirtIoAddressOutOfRange@AEA_KAEA_KAEA_K@Plan9TraceLoggingProvider@@SAXAEA_K00@Z; Plan9TraceLoggingProvider::VirtIoAddressOutOfRange<unsigned __int64 &,unsigned __int64 &,unsigned __int64 &>(unsigned __int64 &,unsigned __int64 &,unsigned __int64 &)
0x18002dffa  mov     [rsp+98h+var_48], 0
0x18002e003  lea     rax, [rsp+98h+var_48]
0x18002e008  mov     [rsp+98h+mappedAddress], rax; mappedAddress
0x18002e00d  xor     r9d, r9d; writeProtected
0x18002e010  mov     r8d, r13d; byteCount
0x18002e013  mov     rdx, r12; guestPhysicalAddress
0x18002e016  mov     rcx, [rbp+20h]; requestor
0x18002e01a  call    cs:__imp_HdvCreateGuestMemoryAperture
0x18002e020  test    eax, eax
0x18002e022  jns     short loc_18002E069
0x18002e024  mov     rcx, [rsp+98h]; this
0x18002e02c  mov     [rsp+98h+var_68], r13d
0x18002e031  mov     [rsp+98h+var_70], r12; char *
0x18002e036  lea     rdx, aMappingDeviceM; "Mapping device memory failed, address %"...
0x18002e03d  mov     [rsp+98h+mappedAddress], rdx; int
0x18002e042  mov     r9d, eax; char *
0x18002e045  lea     r8, aOnecoreVmDvSto_0; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002e04c  mov     edx, 229h; void *
0x18002e051  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002e056  xorps   xmm0, xmm0
0x18002e059  movups  xmmword ptr [rdi+8], xmm0
0x18002e05d  mov     qword ptr [rdi], 0
0x18002e064  jmp     loc_18002E15A
0x18002e069  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002e070  mov     ecx, 20h ; ' '; unsigned __int64
0x18002e075  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002e07a  mov     r14, rax
0x18002e07d  test    rax, rax
0x18002e080  jz      loc_18002E14C
0x18002e086  mov     r13, [rsp+98h+var_48]
0x18002e08b  mov     dword ptr [rax+0Ch], 1
0x18002e092  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::`vftable'
0x18002e099  mov     [r14], rax
0x18002e09c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18002e0a3  test    rcx, rcx
0x18002e0a6  jz      short loc_18002E0B5
0x18002e0a8  mov     rdx, [rcx]
0x18002e0ab  mov     rax, [rdx+8]
0x18002e0af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e0b4  nop
0x18002e0b5  lea     rax, ??_7MemoryAperture@Plan9VirtioDevice@p9fs@@6B@; const p9fs::Plan9VirtioDevice::MemoryAperture::`vftable'
0x18002e0bc  mov     [r14], rax
0x18002e0bf  mov     [r14+10h], rbp
0x18002e0c3  mov     [r14+18h], r13
0x18002e0c7  mov     r13, [rbp+0A0h]
0x18002e0ce  mov     [rbp+0A0h], r14
0x18002e0d5  mov     rax, [r14]
0x18002e0d8  mov     rcx, r14
0x18002e0db  mov     rax, [rax+8]
0x18002e0df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e0e4  test    r13, r13
0x18002e0e7  jz      short loc_18002E0FA
0x18002e0e9  mov     rax, [r13+0]
0x18002e0ed  mov     rcx, r13
0x18002e0f0  mov     rax, [rax+10h]
0x18002e0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e0f9  nop
0x18002e0fa  mov     [r15], r12
0x18002e0fd  mov     rax, [r14+18h]
0x18002e101  mov     [rbp+0B0h], rax
0x18002e108  mov     rcx, [rbp+0A0h]
0x18002e10f  mov     [rdi], rcx
0x18002e112  test    rcx, rcx
0x18002e115  jz      short loc_18002E124
0x18002e117  mov     rax, [rcx]
0x18002e11a  mov     rax, [rax+8]
0x18002e11e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e123  nop
0x18002e124  mov     rax, [rbp+0A8h]
0x18002e12b  mov     [rdi+8], rax
0x18002e12f  mov     rax, [rbp+0B0h]
0x18002e136  mov     [rdi+10h], rax
0x18002e13a  mov     rax, [r14]
0x18002e13d  mov     rcx, r14
0x18002e140  mov     rax, [rax+10h]
0x18002e144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e149  nop
0x18002e14a  jmp     short loc_18002E15A
0x18002e14c  xorps   xmm0, xmm0
0x18002e14f  movups  xmmword ptr [rdi+8], xmm0
0x18002e153  mov     qword ptr [rdi], 0
0x18002e15a  test    rsi, rsi
0x18002e15d  jz      short loc_18002E168
0x18002e15f  mov     rcx, rsi; SRWLock
0x18002e162  call    cs:__imp_ReleaseSRWLockExclusive
0x18002e168  mov     rax, rdi
0x18002e16b  mov     rcx, [rsp+98h+var_40]
0x18002e170  xor     rcx, rsp; StackCookie
0x18002e173  call    __security_check_cookie
0x18002e178  add     rsp, 60h
0x18002e17c  pop     r15
0x18002e17e  pop     r14
0x18002e180  pop     r13
0x18002e182  pop     r12
0x18002e184  pop     rdi
0x18002e185  pop     rsi
0x18002e186  pop     rbp
0x18002e187  retn
```
