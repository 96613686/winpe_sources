# ClientState::SetWnsRegisteredWithWoscService(ushort const *)

- ea: `0x18002b074`
- end: `0x18002b139`
- name: `?SetWnsRegisteredWithWoscService@ClientState@@QEAAXPEBG@Z`
- size: `197`
- prototype: `void(ClientState *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004e774`
- `0x18004e95c`

## callees

- `0x180009e38`
- `0x1800101fc`
- `0x1800266f8`
- `0x18002b074`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b097`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b10d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b097`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b10d`

## string_xrefs

- `0x18002b0db`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`

## pseudocode

```c
void __fastcall ClientState::SetWnsRegisteredWithWoscService(ClientState *this, unsigned __int16 *a2)
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
        (void *)0x56A,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)(unsigned int)v4,
        v7);
    v5 = v10;
    v10 = 0;
    v6 = (void *)*((_QWORD *)this + 57);
    *((_QWORD *)this + 57) = 0;
    CoTaskMemFree(v6);
    *((_QWORD *)this + 57) = v5;
    *((_DWORD *)this + 116) = v9;
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v10);
  }
  else
  {
    v3 = (void *)*((_QWORD *)this + 57);
    *((_QWORD *)this + 57) = 0;
    CoTaskMemFree(v3);
    *((_DWORD *)this + 116) = 0;
  }
}

```

## disassembly

```asm
0x18002b074  mov     [rsp+arg_0], rbx
0x18002b079  push    rdi; int
0x18002b07a  sub     rsp, 20h
0x18002b07e  mov     rax, rdx
0x18002b081  mov     rdi, rcx
0x18002b084  test    rdx, rdx
0x18002b087  jnz     short loc_18002B0AC
0x18002b089  mov     rcx, [rcx+1C8h]; pv
0x18002b090  mov     [rdi+1C8h], rdx
0x18002b097  call    cs:__imp_CoTaskMemFree
0x18002b09d  mov     dword ptr [rdi+1D0h], 0
0x18002b0a7  jmp     loc_18002B12E
0x18002b0ac  mov     [rsp+28h+arg_10], 0
0x18002b0b5  mov     [rsp+28h+arg_8], 0
0x18002b0bd  lea     r8, [rsp+28h+arg_8]
0x18002b0c2  lea     rdx, [rsp+28h+arg_10]
0x18002b0c7  mov     rcx, rax
0x18002b0ca  call    ?CalculateHash@ClientState@@CAJPEBGAEAV?$CCoTaskMemPtr@E@@PEAK@Z; ClientState::CalculateHash(ushort const *,CCoTaskMemPtr<uchar> &,ulong *)
0x18002b0cf  mov     rcx, [rsp+28h]; this
0x18002b0d4  test    eax, eax
0x18002b0d6  jns     short loc_18002B0ED
0x18002b0d8  mov     r9d, eax; char *
0x18002b0db  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x18002b0e2  mov     edx, 56Ah; void *
0x18002b0e7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b0ed  mov     rbx, [rsp+28h+arg_10]
0x18002b0f2  mov     [rsp+28h+arg_10], 0
0x18002b0fb  mov     rcx, [rdi+1C8h]; pv
0x18002b102  mov     qword ptr [rdi+1C8h], 0
0x18002b10d  call    cs:__imp_CoTaskMemFree
0x18002b113  mov     [rdi+1C8h], rbx
0x18002b11a  mov     eax, [rsp+28h+arg_8]
0x18002b11e  mov     [rdi+1D0h], eax
0x18002b124  lea     rcx, [rsp+28h+arg_10]
0x18002b129  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18002b12e  mov     rbx, [rsp+28h+arg_0]
0x18002b133  add     rsp, 20h
0x18002b137  pop     rdi
0x18002b138  retn
```
