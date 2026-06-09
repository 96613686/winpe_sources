# p9fs::Plan9VirtioDevice::CreateRamApertureFromByteRange(unsigned __int64,unsigned __int64,int,void * *,IUnknown * *)

- ea: `0x18002db40`
- end: `0x18002dcaa`
- name: `?CreateRamApertureFromByteRange@Plan9VirtioDevice@p9fs@@UEAAJ_K0HPEAPEAXPEAPEAUIUnknown@@@Z`
- size: `362`
- prototype: `__int64 __fastcall(p9fs::Plan9VirtioDevice *__hidden this, unsigned __int64, unsigned __int64, int, void **, struct IUnknown **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180009fe4`
- `0x18002ca28`
- `0x18002db40`
- `0x18002de94`
- `0x180034010`

## string_xrefs

- `0x18002db8a`: `onecore\vm\dv\storage\plan9\dll\windows\p9virtio.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall p9fs::Plan9VirtioDevice::CreateRamApertureFromByteRange(
        RTL_SRWLOCK *this,
        UINT64 a2,
        unsigned __int64 a3,
        __int64 a4,
        void **a5,
        struct IUnknown **a6)
{
  UINT32 v6; // esi
  __int64 result; // rax
  struct IUnknown *v10; // rbx
  const char *v11; // r9
  struct IUnknown *v12; // rdi
  struct IUnknown *v13; // rcx
  int v14; // [rsp+20h] [rbp-78h]
  unsigned __int8 v15[4]; // [rsp+30h] [rbp-68h] BYREF
  UINT32 v16; // [rsp+34h] [rbp-64h] BYREF
  struct IUnknown *v17; // [rsp+38h] [rbp-60h] BYREF
  struct IUnknown *v18; // [rsp+40h] [rbp-58h]
  UINT64 v19; // [rsp+48h] [rbp-50h] BYREF
  _QWORD v20[9]; // [rsp+50h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v6 = a3;
  v19 = a2;
  if ( a2 <= -(__int64)a3 )
  {
    v18 = 0;
    p9fs::Plan9VirtioDevice::MapDeviceMemory(this, (__int64)v20, (char *)a2, a3);
    try
    {
      v10 = (struct IUnknown *)v20[0];
      if ( v20[0] )
      {
        *a5 = (void *)(v20[2] + a2 - v20[1]);
        v18 = v10;
        ((void (__fastcall *)(struct IUnknown *))v10->lpVtbl->AddRef)(v10);
        v12 = v10;
      }
      else
      {
        v17 = 0;
        v15[0] = 0;
        v16 = v6;
        wil::MakeOrThrow<p9fs::Plan9VirtioDevice::MemoryAperture,p9fs::Plan9VirtioDevice &,unsigned __int64 &,unsigned int,bool>(
          &v17,
          (__int64)this,
          &v19,
          &v16,
          v15);
        v13 = v17;
        *a5 = v17[3].lpVtbl;
        v12 = v13;
        v18 = v13;
        if ( v13 )
        {
          ((void (__fastcall *)(struct IUnknown *))v13->lpVtbl->AddRef)(v13);
          v13 = v17;
        }
        if ( v13 )
        {
          v17 = 0;
          ((void (__fastcall *)(struct IUnknown *))v13->lpVtbl->Release)(v13);
        }
      }
      v18 = 0;
      *a6 = v12;
      if ( v10 )
        ((void (__fastcall *)(struct IUnknown *))v10->lpVtbl->Release)(v10);
      result = 0;
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x125,
                             (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9virtio.cpp",
                             v11);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x108,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9virtio.cpp",
      (const char *)0x80070057LL,
      v14);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x18002db40  mov     [rsp+arg_18], rbx
0x18002db45  push    rsi
0x18002db46  push    rdi
0x18002db47  push    r12
0x18002db49  push    r14
0x18002db4b  push    r15
0x18002db4d  sub     rsp, 70h
0x18002db51  mov     rsi, r8
0x18002db54  mov     rdi, rdx
0x18002db57  mov     r15, rcx
0x18002db5a  mov     [rsp+98h+var_50], rdx
0x18002db5f  mov     r14, [rsp+98h+arg_20]
0x18002db67  mov     r12, [rsp+98h+arg_28]
0x18002db6f  mov     rax, r8
0x18002db72  neg     rax
0x18002db75  cmp     rdx, rax
0x18002db78  jbe     short loc_18002DBA2
0x18002db7a  mov     rcx, [rsp+98h]; this
0x18002db82  mov     ebx, 80070057h
0x18002db87  mov     r9d, ebx; char *
0x18002db8a  lea     r8, aOnecoreVmDvSto_0; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002db91  mov     edx, 108h; void *
0x18002db96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002db9b  mov     eax, ebx
0x18002db9d  jmp     loc_18002DC94
0x18002dba2  mov     [rsp+98h+var_58], 0
0x18002dbab  mov     r9, rsi
0x18002dbae  mov     r8, rdi
0x18002dbb1  lea     rdx, [rsp+98h+var_48]
0x18002dbb6  call    ?MapDeviceMemory@Plan9VirtioDevice@p9fs@@AEAA?AUDeviceMemory@12@_K0@Z; p9fs::Plan9VirtioDevice::MapDeviceMemory(unsigned __int64,unsigned __int64)
0x18002dbbb  nop
0x18002dbbc  mov     rbx, [rsp+98h+var_48]
0x18002dbc1  test    rbx, rbx
0x18002dbc4  jz      short loc_18002DBF2
0x18002dbc6  sub     rdi, [rsp+98h+var_40]
0x18002dbcb  add     rdi, [rsp+98h+var_38]
0x18002dbd0  mov     [r14], rdi
0x18002dbd3  mov     [rsp+98h+var_58], rbx
0x18002dbd8  test    rbx, rbx
0x18002dbdb  jz      short loc_18002DBED
0x18002dbdd  mov     rax, [rbx]
0x18002dbe0  mov     rcx, rbx
0x18002dbe3  mov     rax, [rax+8]
0x18002dbe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dbec  nop
0x18002dbed  mov     rdi, rbx
0x18002dbf0  jmp     short loc_18002DC6A
0x18002dbf2  mov     [rsp+98h+var_60], 0
0x18002dbfb  mov     [rsp+98h+var_68], 0
0x18002dc00  mov     [rsp+98h+var_64], esi
0x18002dc04  lea     rax, [rsp+98h+var_68]
0x18002dc09  mov     qword ptr [rsp+98h+var_78], rax
0x18002dc0e  lea     r9, [rsp+98h+var_64]
0x18002dc13  lea     r8, [rsp+98h+var_50]
0x18002dc18  mov     rdx, r15
0x18002dc1b  lea     rcx, [rsp+98h+var_60]
0x18002dc20  call    ??$MakeOrThrow@VMemoryAperture@Plan9VirtioDevice@p9fs@@AEAV23@AEA_KI_N@wil@@YA?AV?$ComPtr@VMemoryAperture@Plan9VirtioDevice@p9fs@@@WRL@Microsoft@@AEAVPlan9VirtioDevice@p9fs@@AEA_K$$QEAI$$QEA_N@Z; wil::MakeOrThrow<p9fs::Plan9VirtioDevice::MemoryAperture,p9fs::Plan9VirtioDevice &,unsigned __int64 &,uint,bool>(p9fs::Plan9VirtioDevice &,unsigned __int64 &,uint &&,bool &&)
0x18002dc25  mov     rcx, [rsp+98h+var_60]
0x18002dc2a  mov     rax, [rcx+18h]
0x18002dc2e  mov     [r14], rax
0x18002dc31  mov     rdi, rcx
0x18002dc34  mov     [rsp+98h+var_58], rcx
0x18002dc39  test    rcx, rcx
0x18002dc3c  jz      short loc_18002DC4F
0x18002dc3e  mov     rax, [rcx]
0x18002dc41  mov     rax, [rax+8]
0x18002dc45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc4a  mov     rcx, [rsp+98h+var_60]
0x18002dc4f  test    rcx, rcx
0x18002dc52  jz      short loc_18002DC6A
0x18002dc54  mov     [rsp+98h+var_60], 0
0x18002dc5d  mov     rax, [rcx]
0x18002dc60  mov     rax, [rax+10h]
0x18002dc64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc69  nop
0x18002dc6a  mov     [rsp+98h+var_58], 0
0x18002dc73  mov     [r12], rdi
0x18002dc77  test    rbx, rbx
0x18002dc7a  jz      short loc_18002DC8C
0x18002dc7c  mov     rax, [rbx]
0x18002dc7f  mov     rcx, rbx
0x18002dc82  mov     rax, [rax+10h]
0x18002dc86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc8b  nop
0x18002dc8c  xor     eax, eax
0x18002dc8e  jmp     short loc_18002DC94
0x18002dc90  mov     eax, [rsp+98h+var_64]
0x18002dc94  mov     rbx, [rsp+98h+arg_18]
0x18002dc9c  add     rsp, 70h
0x18002dca0  pop     r15
0x18002dca2  pop     r14
0x18002dca4  pop     r12
0x18002dca6  pop     rdi
0x18002dca7  pop     rsi
0x18002dca8  retn
```
