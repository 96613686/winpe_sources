# ClusApi::Cluster::GetClusterSecret(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x18002e5b0`
- end: `0x18002e622`
- name: `?GetClusterSecret@Cluster@ClusApi@@UEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18000f3e8`
- `0x1800112f0`
- `0x18002e5b0`

## import_xrefs

- `CLUSAPI!CCHlpGetClusterServiceSecret` at `0x18002e5d5`
- `CLUSAPI!CCHlpGetClusterServiceSecret` at `0x18002e5d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ClusApi::Cluster::GetClusterSecret(__int64 a1, __int64 a2)
{
  int ClusterServiceSecret; // edi
  wchar_t *v4; // rbx
  _BYTE v6[8]; // [rsp+20h] [rbp-18h] BYREF
  wchar_t *v7; // [rsp+28h] [rbp-10h]
  wchar_t *v8; // [rsp+50h] [rbp+18h] BYREF

  v8 = 0;
  v7 = 0;
  ClusterServiceSecret = CCHlpGetClusterServiceSecret(0, &v8);
  if ( ClusterServiceSecret >= 0 )
  {
    std::wstring::assign(a2, v8);
    v4 = v8;
    cxl::LocalHeapPtr<unsigned char>::Clear(v6);
    v7 = v4;
    v8 = 0;
  }
  cxl::LocalHeapPtr<unsigned char>::Clear(v6);
  return (unsigned int)ClusterServiceSecret;
}

```

## disassembly

```asm
0x18002e5b0  mov     rax, rsp
0x18002e5b3  mov     [rax+8], rbx
0x18002e5b7  push    rdi
0x18002e5b8  sub     rsp, 30h
0x18002e5bc  mov     rbx, rdx
0x18002e5bf  mov     qword ptr [rax+18h], 0
0x18002e5c7  mov     qword ptr [rax-10h], 0
0x18002e5cf  lea     rdx, [rax+18h]
0x18002e5d3  xor     ecx, ecx
0x18002e5d5  call    cs:__imp_?CCHlpGetClusterServiceSecret@@YAJPEB_WPEAPEA_W@Z; CCHlpGetClusterServiceSecret(wchar_t const *,wchar_t * *)
0x18002e5db  mov     edi, eax
0x18002e5dd  test    eax, eax
0x18002e5df  js      short loc_18002E60B
0x18002e5e1  mov     rdx, [rsp+38h+arg_10]
0x18002e5e6  mov     rcx, rbx
0x18002e5e9  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18002e5ee  mov     rbx, [rsp+38h+arg_10]
0x18002e5f3  lea     rcx, [rsp+38h+var_18]
0x18002e5f8  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x18002e5fd  mov     [rsp+38h+var_10], rbx
0x18002e602  mov     [rsp+38h+arg_10], 0
0x18002e60b  lea     rcx, [rsp+38h+var_18]
0x18002e610  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x18002e615  mov     eax, edi
0x18002e617  mov     rbx, [rsp+38h+arg_0]
0x18002e61c  add     rsp, 30h
0x18002e620  pop     rdi
0x18002e621  retn
```
