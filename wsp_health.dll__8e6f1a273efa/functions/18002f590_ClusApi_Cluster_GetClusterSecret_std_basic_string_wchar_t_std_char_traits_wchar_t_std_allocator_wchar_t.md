# ClusApi::Cluster::GetClusterSecret(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x18002f590`
- end: `0x18002f609`
- name: `?GetClusterSecret@Cluster@ClusApi@@UEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18000f89c`
- `0x180011800`
- `0x18002f590`

## import_xrefs

- `CLUSAPI!CCHlpGetClusterServiceSecret` at `0x18002f5b5`
- `CLUSAPI!CCHlpGetClusterServiceSecret` at `0x18002f5b5`

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
0x18002f590  mov     rax, rsp
0x18002f593  mov     [rax+8], rbx
0x18002f597  push    rdi
0x18002f598  sub     rsp, 30h
0x18002f59c  mov     rbx, rdx
0x18002f59f  mov     qword ptr [rax+18h], 0
0x18002f5a7  mov     qword ptr [rax-10h], 0
0x18002f5af  lea     rdx, [rax+18h]
0x18002f5b3  xor     ecx, ecx
0x18002f5b5  call    cs:__imp_?CCHlpGetClusterServiceSecret@@YAJPEB_WPEAPEA_W@Z; CCHlpGetClusterServiceSecret(wchar_t const *,wchar_t * *)
0x18002f5bc  nop     dword ptr [rax+rax+00h]
0x18002f5c1  mov     edi, eax
0x18002f5c3  test    eax, eax
0x18002f5c5  js      short loc_18002F5F1
0x18002f5c7  mov     rdx, [rsp+38h+arg_10]
0x18002f5cc  mov     rcx, rbx
0x18002f5cf  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18002f5d4  mov     rbx, [rsp+38h+arg_10]
0x18002f5d9  lea     rcx, [rsp+38h+var_18]
0x18002f5de  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x18002f5e3  mov     [rsp+38h+var_10], rbx
0x18002f5e8  mov     [rsp+38h+arg_10], 0
0x18002f5f1  lea     rcx, [rsp+38h+var_18]
0x18002f5f6  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x18002f5fb  mov     eax, edi
0x18002f5fd  mov     rbx, [rsp+38h+arg_0]
0x18002f602  add     rsp, 30h
0x18002f606  pop     rdi
0x18002f607  retn
```
