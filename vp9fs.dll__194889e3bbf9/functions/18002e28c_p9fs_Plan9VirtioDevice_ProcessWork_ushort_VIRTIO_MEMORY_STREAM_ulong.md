# p9fs::Plan9VirtioDevice::ProcessWork(ushort,_VIRTIO_MEMORY_STREAM *,ulong *)

- ea: `0x18002e28c`
- end: `0x18002e456`
- name: `?ProcessWork@Plan9VirtioDevice@p9fs@@AEAAJGPEAU_VIRTIO_MEMORY_STREAM@@PEAK@Z`
- size: `458`
- prototype: `__int64 __fastcall(p9fs::Plan9VirtioDevice *__hidden this, unsigned __int16, struct _VIRTIO_MEMORY_STREAM *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18002e280`

## callees

- `0x180004120`
- `0x18000d498`
- `0x18000e23c`
- `0x18001c75c`
- `0x18001c93c`
- `0x18002e190`
- `0x18002e28c`
- `0x180034010`

## import_xrefs

- `vmvirtio!VirtioMemoryStreamGetCurrentWriteSpanLength` at `0x18002e36d`
- `vmvirtio!VirtioMemoryStreamGetCurrentWriteSpanLength` at `0x18002e36d`
- `vmvirtio!VirtioMemoryStreamRead` at `0x18002e354`
- `vmvirtio!VirtioMemoryStreamRead` at `0x18002e354`
- `vmvirtio!VirtioMemoryStreamGetCurrentReadSpanLength` at `0x18002e312`
- `vmvirtio!VirtioMemoryStreamGetCurrentReadSpanLength` at `0x18002e312`

## string_xrefs

- `0x18002e43d`: `onecore\vm\dv\storage\plan9\dll\windows\p9virtio.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall p9fs::Plan9VirtioDevice::ProcessWork(
        p9fs::Plan9VirtioDevice *this,
        __int16 a2,
        struct _VIRTIO_MEMORY_STREAM *a3,
        unsigned int *a4)
{
  gsl::details *v8; // rcx
  __int64 v9; // rdx
  __int64 SpanLength; // rdi
  int v11; // eax
  __int64 v12; // r8
  __int64 v13; // r10
  void (__fastcall *v14)(__int64, __int128 *, __int64, _QWORD *); // rax
  _QWORD *v15; // rdx
  const char *v16; // r9
  __int64 result; // rax
  int v18; // [rsp+20h] [rbp-B8h]
  _QWORD v19[2]; // [rsp+40h] [rbp-98h] BYREF
  _QWORD v20[2]; // [rsp+50h] [rbp-88h] BYREF
  __int16 v21; // [rsp+60h] [rbp-78h]
  int v22; // [rsp+62h] [rbp-76h]
  __int16 v23; // [rsp+66h] [rbp-72h]
  struct _VIRTIO_MEMORY_STREAM *v24; // [rsp+68h] [rbp-70h]
  _QWORD *v25; // [rsp+88h] [rbp-50h]
  __int128 v26; // [rsp+90h] [rbp-48h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  try
  {
    if ( !*((_BYTE *)this + 144) )
    {
      *((_BYTE *)this + 144) = 1;
      v8 = (gsl::details *)*((_QWORD *)this + 10);
      if ( !v8 || (v9 = *(unsigned __int16 *)v8, (v8 = (gsl::details *)((char *)v8 + 2)) == 0) && v9 )
        gsl::details::terminate(v8);
      v19[0] = v8;
      v19[1] = v9;
      p9fs::Plan9DeviceHost::NotifyDeviceInUse(*((_QWORD *)this + 7), v19);
    }
    SpanLength = VirtioMemoryStreamGetCurrentReadSpanLength(a3);
    v26 = 0;
    v27 = 0;
    if ( SpanLength )
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&v26, SpanLength);
    v11 = VirtioMemoryStreamRead(a3, v26, SpanLength);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1DC,
        (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9virtio.cpp",
        (const char *)(unsigned int)v11,
        v18);
    v12 = VirtioMemoryStreamGetCurrentWriteSpanLength(a3);
    v13 = *((_QWORD *)this + 9);
    v14 = *(void (__fastcall **)(__int64, __int128 *, __int64, _QWORD *))(*(_QWORD *)v13 + 8LL);
    v20[0] = &std::_Func_impl_no_alloc<_lambda_27e1a999759112350a61f42c5c52127a_,void,std::vector<enum gsl::byte> const &>::`vftable';
    v20[1] = this;
    v21 = a2;
    v22 = *(_DWORD *)((char *)&v26 + 10);
    v23 = HIWORD(v26);
    v24 = a3;
    v25 = v20;
    v14(v13, &v26, v12, v20);
    if ( v25 )
    {
      v15 = v20;
      LOBYTE(v15) = v25 != v20;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v25 + 32LL))(v25, v15);
    }
    *a4 = 0;
    std::vector<unsigned char>::~vector<unsigned char>(&v26);
    result = 2147483658LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1F2,
                           (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9virtio.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x18002e28c  push    rbx
0x18002e28e  push    rsi
0x18002e28f  push    rdi
0x18002e290  push    r14
0x18002e292  push    r15
0x18002e294  sub     rsp, 0B0h
0x18002e29b  mov     rax, cs:__security_cookie
0x18002e2a2  xor     rax, rsp
0x18002e2a5  mov     [rsp+0D8h+var_30], rax
0x18002e2ad  mov     r14, r9
0x18002e2b0  mov     rsi, r8
0x18002e2b3  movzx   r15d, dx
0x18002e2b7  mov     rbx, rcx
0x18002e2ba  cmp     byte ptr [rcx+90h], 0
0x18002e2c1  jnz     short loc_18002E30F
0x18002e2c3  mov     byte ptr [rcx+90h], 1
0x18002e2ca  mov     rcx, [rcx+50h]; this
0x18002e2ce  test    rcx, rcx
0x18002e2d1  jz      loc_18002E44F
0x18002e2d7  movzx   edx, word ptr [rcx]
0x18002e2da  lea     rax, [rdx+2]
0x18002e2de  cmp     rax, 2
0x18002e2e2  jb      loc_18002E44F
0x18002e2e8  add     rcx, 2
0x18002e2ec  jnz     short loc_18002E2F7
0x18002e2ee  test    rdx, rdx
0x18002e2f1  jnz     loc_18002E44F
0x18002e2f7  mov     [rsp+0D8h+var_98], rcx
0x18002e2fc  mov     [rsp+0D8h+var_90], rdx
0x18002e301  lea     rdx, [rsp+0D8h+var_98]
0x18002e306  mov     rcx, [rbx+38h]
0x18002e30a  call    ?NotifyDeviceInUse@Plan9DeviceHost@p9fs@@QEAAXV?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; p9fs::Plan9DeviceHost::NotifyDeviceInUse(std::string_view)
0x18002e30f  mov     rcx, rsi
0x18002e312  call    cs:__imp_VirtioMemoryStreamGetCurrentReadSpanLength
0x18002e318  mov     rdi, rax
0x18002e31b  xor     eax, eax
0x18002e31d  xorps   xmm1, xmm1
0x18002e320  movdqu  [rsp+0D8h+var_48], xmm1
0x18002e329  mov     [rsp+0D8h+var_38], rax
0x18002e331  test    rdi, rdi
0x18002e334  jz      short loc_18002E346
0x18002e336  mov     rdx, rdi
0x18002e339  lea     rcx, [rsp+0D8h+var_48]
0x18002e341  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002e346  mov     r8, rdi
0x18002e349  mov     rdx, qword ptr [rsp+0D8h+var_48]
0x18002e351  mov     rcx, rsi
0x18002e354  call    cs:__imp_VirtioMemoryStreamRead
0x18002e35a  mov     rcx, [rsp+0D8h]; this
0x18002e362  test    eax, eax
0x18002e364  js      loc_18002E43A
0x18002e36a  mov     rcx, rsi
0x18002e36d  call    cs:__imp_VirtioMemoryStreamGetCurrentWriteSpanLength
0x18002e373  mov     r8, rax
0x18002e376  mov     r10, [rbx+48h]
0x18002e37a  mov     rcx, [r10]
0x18002e37d  mov     rax, [rcx+8]
0x18002e381  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_27e1a999759112350a61f42c5c52127a_@@XAEBV?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_27e1a999759112350a61f42c5c52127a_,void,std::vector<gsl::byte> const &>::`vftable'
0x18002e388  mov     [rsp+0D8h+var_88], rcx
0x18002e38d  mov     [rsp+0D8h+var_80], rbx
0x18002e392  mov     [rsp+0D8h+var_78], r15w
0x18002e398  mov     edx, dword ptr [rsp+0D8h+var_48+0Ah]
0x18002e39f  mov     [rsp+0D8h+var_76], edx
0x18002e3a3  movzx   edx, word ptr [rsp+0D8h+var_48+0Eh]
0x18002e3ab  mov     [rsp+0D8h+var_72], dx
0x18002e3b0  mov     [rsp+0D8h+var_70], rsi
0x18002e3b5  lea     rcx, [rsp+0D8h+var_88]
0x18002e3ba  mov     [rsp+0D8h+var_50], rcx
0x18002e3c2  lea     r9, [rsp+0D8h+var_88]
0x18002e3c7  lea     rdx, [rsp+0D8h+var_48]
0x18002e3cf  mov     rcx, r10
0x18002e3d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3d7  nop
0x18002e3d8  mov     rcx, [rsp+0D8h+var_50]
0x18002e3e0  test    rcx, rcx
0x18002e3e3  jz      short loc_18002E3FC
0x18002e3e5  mov     rax, [rcx]
0x18002e3e8  lea     rdx, [rsp+0D8h+var_88]
0x18002e3ed  cmp     rcx, rdx
0x18002e3f0  setnz   dl
0x18002e3f3  mov     rax, [rax+20h]
0x18002e3f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3fc  mov     dword ptr [r14], 0
0x18002e403  lea     rcx, [rsp+0D8h+var_48]
0x18002e40b  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18002e410  mov     eax, 8000000Ah
0x18002e415  jmp     short loc_18002E41B
0x18002e417  mov     eax, [rsp+0D8h+var_A8]
0x18002e41b  mov     rcx, [rsp+0D8h+var_30]
0x18002e423  xor     rcx, rsp; StackCookie
0x18002e426  call    __security_check_cookie
0x18002e42b  add     rsp, 0B0h
0x18002e432  pop     r15
0x18002e434  pop     r14
0x18002e436  pop     rdi
0x18002e437  pop     rsi
0x18002e438  pop     rbx
0x18002e439  retn
0x18002e43a  mov     r9d, eax; char *
0x18002e43d  lea     r8, aOnecoreVmDvSto_0; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002e444  mov     edx, 1DCh; void *
0x18002e449  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002e44f  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
```
