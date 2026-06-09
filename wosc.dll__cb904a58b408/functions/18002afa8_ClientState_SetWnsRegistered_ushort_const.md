# ClientState::SetWnsRegistered(ushort const *)

- ea: `0x18002afa8`
- end: `0x18002b06d`
- name: `?SetWnsRegistered@ClientState@@QEAAXPEBG@Z`
- size: `197`
- prototype: `void(ClientState *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004e028`
- `0x18004e5b8`

## callees

- `0x180009e38`
- `0x1800101fc`
- `0x1800266f8`
- `0x18002afa8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002afcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b041`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002afcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b041`

## string_xrefs

- `0x18002b00f`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ClientState::SetWnsRegistered(ClientState *this, unsigned __int16 *a2)
{
  void *v3; // rcx
  int v4; // eax
  void *v5; // rbx
  void *v6; // rcx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v9; // [rsp+38h] [rbp+10h] BYREF
  void *v10; // [rsp+40h] [rbp+18h] BYREF

  if ( a2 )
  {
    v10 = 0;
    v9 = 0;
    v4 = ClientState::CalculateHash(a2, &v10, &v9);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x553,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)(unsigned int)v4,
        v7);
    v5 = v10;
    v10 = 0;
    v6 = (void *)*((_QWORD *)this + 54);
    *((_QWORD *)this + 54) = 0;
    CoTaskMemFree(v6);
    *((_QWORD *)this + 54) = v5;
    *((_DWORD *)this + 110) = v9;
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v10);
  }
  else
  {
    v3 = (void *)*((_QWORD *)this + 54);
    *((_QWORD *)this + 54) = 0;
    CoTaskMemFree(v3);
    *((_DWORD *)this + 110) = 0;
  }
}

```

## disassembly

```asm
0x18002afa8  mov     [rsp+arg_0], rbx
0x18002afad  push    rdi; int
0x18002afae  sub     rsp, 20h
0x18002afb2  mov     rax, rdx
0x18002afb5  mov     rdi, rcx
0x18002afb8  test    rdx, rdx
0x18002afbb  jnz     short loc_18002AFE0
0x18002afbd  mov     rcx, [rcx+1B0h]; pv
0x18002afc4  mov     [rdi+1B0h], rdx
0x18002afcb  call    cs:__imp_CoTaskMemFree
0x18002afd1  mov     dword ptr [rdi+1B8h], 0
0x18002afdb  jmp     loc_18002B062
0x18002afe0  mov     [rsp+28h+arg_10], 0
0x18002afe9  mov     [rsp+28h+arg_8], 0
0x18002aff1  lea     r8, [rsp+28h+arg_8]
0x18002aff6  lea     rdx, [rsp+28h+arg_10]
0x18002affb  mov     rcx, rax
0x18002affe  call    ?CalculateHash@ClientState@@CAJPEBGAEAV?$CCoTaskMemPtr@E@@PEAK@Z; ClientState::CalculateHash(ushort const *,CCoTaskMemPtr<uchar> &,ulong *)
0x18002b003  mov     rcx, [rsp+28h]; this
0x18002b008  test    eax, eax
0x18002b00a  jns     short loc_18002B021
0x18002b00c  mov     r9d, eax; char *
0x18002b00f  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x18002b016  mov     edx, 553h; void *
0x18002b01b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b021  mov     rbx, [rsp+28h+arg_10]
0x18002b026  mov     [rsp+28h+arg_10], 0
0x18002b02f  mov     rcx, [rdi+1B0h]; pv
0x18002b036  mov     qword ptr [rdi+1B0h], 0
0x18002b041  call    cs:__imp_CoTaskMemFree
0x18002b047  mov     [rdi+1B0h], rbx
0x18002b04e  mov     eax, [rsp+28h+arg_8]
0x18002b052  mov     [rdi+1B8h], eax
0x18002b058  lea     rcx, [rsp+28h+arg_10]
0x18002b05d  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18002b062  mov     rbx, [rsp+28h+arg_0]
0x18002b067  add     rsp, 20h
0x18002b06b  pop     rdi
0x18002b06c  retn
```
