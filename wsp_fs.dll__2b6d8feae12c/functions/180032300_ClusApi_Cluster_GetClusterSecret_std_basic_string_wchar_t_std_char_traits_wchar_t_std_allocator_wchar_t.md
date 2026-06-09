# ClusApi::Cluster::GetClusterSecret(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180032300`
- end: `0x180032372`
- name: `?GetClusterSecret@Cluster@ClusApi@@UEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18001072c`
- `0x180012660`
- `0x180032300`

## import_xrefs

- `CLUSAPI!CCHlpGetClusterServiceSecret` at `0x180032325`
- `CLUSAPI!CCHlpGetClusterServiceSecret` at `0x180032325`

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
    std::wstring::assign(a2);
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
0x180032300  mov     rax, rsp
0x180032303  mov     [rax+8], rbx
0x180032307  push    rdi
0x180032308  sub     rsp, 30h
0x18003230c  mov     rbx, rdx
0x18003230f  mov     qword ptr [rax+18h], 0
0x180032317  mov     qword ptr [rax-10h], 0
0x18003231f  lea     rdx, [rax+18h]
0x180032323  xor     ecx, ecx
0x180032325  call    cs:__imp_?CCHlpGetClusterServiceSecret@@YAJPEB_WPEAPEA_W@Z; CCHlpGetClusterServiceSecret(wchar_t const *,wchar_t * *)
0x18003232b  mov     edi, eax
0x18003232d  test    eax, eax
0x18003232f  js      short loc_18003235B
0x180032331  mov     rdx, [rsp+38h+arg_10]
0x180032336  mov     rcx, rbx
0x180032339  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18003233e  mov     rbx, [rsp+38h+arg_10]
0x180032343  lea     rcx, [rsp+38h+var_18]
0x180032348  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x18003234d  mov     [rsp+38h+var_10], rbx
0x180032352  mov     [rsp+38h+arg_10], 0
0x18003235b  lea     rcx, [rsp+38h+var_18]
0x180032360  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180032365  mov     eax, edi
0x180032367  mov     rbx, [rsp+38h+arg_0]
0x18003236c  add     rsp, 30h
0x180032370  pop     rdi
0x180032371  retn
```
