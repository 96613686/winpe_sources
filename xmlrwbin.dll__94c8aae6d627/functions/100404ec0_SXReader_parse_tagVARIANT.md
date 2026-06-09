# SXReader::parse(tagVARIANT)

- ea: `0x100404ec0`
- end: `0x100404f70`
- name: `?parse@SXReader@@UEAAJUtagVARIANT@@@Z`
- size: `176`
- prototype: `int(SXReader *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x100404ec0`
- `0x100404f80`
- `0x1004112e0`
- `0x1004138b0`
- `0x100414090`
- `0x100424580`

## pseudocode

```c
__int64 __fastcall SXReader::parse(SXReader *this, struct tagVARIANT *a2)
{
  struct IUnknown *Unknown; // rax
  struct IStream *v5; // [rsp+60h] [rbp+18h] BYREF
  struct IUnknown *v6; // [rsp+68h] [rbp+20h]

  Unknown = Variant::getUnknown(a2, 0);
  v6 = Unknown;
  if ( Unknown )
  {
    if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IStream **))Unknown->lpVtbl->QueryInterface)(
           Unknown,
           &IID_ISequentialStream,
           &v5) >= 0
      || (_mm_lfence(),
          ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IStream **))v6->lpVtbl->QueryInterface)(
            v6,
            &IID_IStream,
            &v5) >= 0) )
    {
      if ( v5 )
      {
        SXReadBase::SetStream((SXReader *)((char *)this - 1456), v5);
        ((void (__fastcall *)(struct IStream *))v5->lpVtbl->Release)(v5);
      }
    }
  }
  SXReader::ParseSXStream((SXReader *)((char *)this - 1456));
  return 0;
}

```

## disassembly

```asm
0x100404ec0  mov     [rsp+arg_0], rbx
0x100404ec5  push    rdi
0x100404ec6  sub     rsp, 40h
0x100404eca  mov     rax, rdx
0x100404ecd  mov     rdi, rcx
0x100404ed0  xor     ebx, ebx
0x100404ed2  xor     edx, edx; bool
0x100404ed4  mov     rcx, rax; struct tagVARIANT *
0x100404ed7  call    ?getUnknown@Variant@@SAPEAUIUnknown@@PEAUtagVARIANT@@_N@Z; Variant::getUnknown(tagVARIANT *,bool)
0x100404edc  mov     rcx, rax
0x100404edf  mov     [rsp+48h+arg_18], rax
0x100404ee4  test    rax, rax
0x100404ee7  jz      short loc_100404F51
0x100404ee9  mov     rax, [rax]
0x100404eec  lea     r8, [rsp+48h+arg_10]
0x100404ef1  lea     rdx, IID_ISequentialStream
0x100404ef8  mov     rax, [rax]
0x100404efb  call    cs:__guard_dispatch_icall_fptr
0x100404f01  test    eax, eax
0x100404f03  jns     short loc_100404F29
0x100404f05  lfence
0x100404f08  mov     rcx, [rsp+48h+arg_18]
0x100404f0d  mov     rax, [rcx]
0x100404f10  lea     r8, [rsp+48h+arg_10]
0x100404f15  lea     rdx, IID_IStream
0x100404f1c  mov     rax, [rax]
0x100404f1f  call    cs:__guard_dispatch_icall_fptr
0x100404f25  test    eax, eax
0x100404f27  js      short loc_100404F51
0x100404f29  mov     rdx, [rsp+48h+arg_10]; struct IStream *
0x100404f2e  test    rdx, rdx
0x100404f31  jz      short loc_100404F51
0x100404f33  lea     rcx, [rdi-5B0h]; this
0x100404f3a  call    ?SetStream@SXReadBase@@IEAAXPEAUIStream@@@Z; SXReadBase::SetStream(IStream *)
0x100404f3f  mov     rcx, [rsp+48h+arg_10]
0x100404f44  mov     rax, [rcx]
0x100404f47  mov     rax, [rax+10h]
0x100404f4b  call    cs:__guard_dispatch_icall_fptr
0x100404f51  lea     rcx, [rdi-5B0h]; this
0x100404f58  call    ?ParseSXStream@SXReader@@AEAAXXZ; SXReader::ParseSXStream(void)
0x100404f5d  jmp     short loc_100404F63
0x100404f5f  mov     ebx, [rsp+48h+var_28]
0x100404f63  mov     eax, ebx
0x100404f65  mov     rbx, [rsp+48h+arg_0]
0x100404f6a  add     rsp, 40h
0x100404f6e  pop     rdi
0x100404f6f  retn
0x100424620  push    rbp
0x100424622  sub     rsp, 20h
0x100424626  mov     rbp, rdx
0x100424629  mov     [rbp+38h], rcx
0x10042462d  mov     [rbp+30h], rcx
0x100424631  mov     rax, [rbp+30h]
0x100424635  mov     rcx, [rax]
0x100424638  mov     [rbp+28h], rcx
0x10042463c  mov     rax, [rbp+28h]
0x100424640  mov     eax, [rax]
0x100424642  cmp     eax, 0C0000005h
0x100424647  jz      short loc_100424679
0x100424649  add     eax, 1FFFFFFFh
0x10042464e  cmp     eax, 1
0x100424651  ja      short loc_100424669
0x100424653  mov     rax, [rbp+28h]
0x100424657  cmp     dword ptr [rax+18h], 1
0x10042465b  jnz     short loc_100424669
0x10042465d  mov     rax, [rbp+28h]
0x100424661  mov     ecx, [rax+20h]
0x100424664  mov     [rbp+20h], ecx
0x100424667  jmp     short loc_100424670
0x100424669  mov     dword ptr [rbp+20h], 8000FFFFh
0x100424670  mov     dword ptr [rbp+24h], 1
0x100424677  jmp     short loc_100424680
0x100424679  mov     dword ptr [rbp+24h], 0
0x100424680  mov     eax, [rbp+24h]
0x100424683  add     rsp, 20h
0x100424687  pop     rbp
0x100424688  retn
```
