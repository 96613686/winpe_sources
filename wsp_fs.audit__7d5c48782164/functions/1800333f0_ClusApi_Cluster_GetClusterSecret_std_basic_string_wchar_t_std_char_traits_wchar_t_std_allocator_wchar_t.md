# ClusApi::Cluster::GetClusterSecret(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1800333f0`
- end: `0x180033469`
- name: `?GetClusterSecret@Cluster@ClusApi@@UEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180010b90`
- `0x180012b00`
- `0x1800333f0`

## import_xrefs

- `CLUSAPI!CCHlpGetClusterServiceSecret` at `0x180033415`
- `CLUSAPI!CCHlpGetClusterServiceSecret` at `0x180033415`

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
0x1800333f0  mov     rax, rsp
0x1800333f3  mov     [rax+8], rbx
0x1800333f7  push    rdi
0x1800333f8  sub     rsp, 30h
0x1800333fc  mov     rbx, rdx
0x1800333ff  mov     qword ptr [rax+18h], 0
0x180033407  mov     qword ptr [rax-10h], 0
0x18003340f  lea     rdx, [rax+18h]
0x180033413  xor     ecx, ecx
0x180033415  call    cs:__imp_?CCHlpGetClusterServiceSecret@@YAJPEB_WPEAPEA_W@Z; CCHlpGetClusterServiceSecret(wchar_t const *,wchar_t * *)
0x18003341c  nop     dword ptr [rax+rax+00h]
0x180033421  mov     edi, eax
0x180033423  test    eax, eax
0x180033425  js      short loc_180033451
0x180033427  mov     rdx, [rsp+38h+arg_10]
0x18003342c  mov     rcx, rbx
0x18003342f  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180033434  mov     rbx, [rsp+38h+arg_10]
0x180033439  lea     rcx, [rsp+38h+var_18]
0x18003343e  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180033443  mov     [rsp+38h+var_10], rbx
0x180033448  mov     [rsp+38h+arg_10], 0
0x180033451  lea     rcx, [rsp+38h+var_18]
0x180033456  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x18003345b  mov     eax, edi
0x18003345d  mov     rbx, [rsp+38h+arg_0]
0x180033462  add     rsp, 30h
0x180033466  pop     rdi
0x180033467  retn
```
