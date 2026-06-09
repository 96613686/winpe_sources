# XMLScrSite::AddRuntimeNamed(ushort *,ushort *,__MIDL___MIDL_itf_sct_0000_0005_0002,int)

- ea: `0x14000bda0`
- end: `0x14000be69`
- name: `?AddRuntimeNamed@XMLScrSite@@UEAAJPEAG0W4__MIDL___MIDL_itf_sct_0000_0005_0002@@H@Z`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000bda0`
- `0x140018010`

## pseudocode

```c
__int64 __fastcall XMLScrSite::AddRuntimeNamed(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, int a5)
{
  __int64 v5; // rax
  int v9; // ebx
  _QWORD v11[7]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v12; // [rsp+70h] [rbp+8h] BYREF

  v5 = *(_QWORD *)(a1 + 16);
  v12 = 0;
  v11[0] = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(v5 + 624) + 128LL))(*(_QWORD *)(v5 + 624), &v12);
  if ( v9 >= 0 )
  {
    v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v12)(v12, &IID_IWshRuntime, v11);
    if ( v9 >= 0 )
      v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, int))(*(_QWORD *)v11[0] + 24LL))(
             v11[0],
             a2,
             a3,
             a4,
             a5);
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v11[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v11[0] + 16LL))(v11[0]);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14000bda0  push    rbx
0x14000bda2  push    rbp
0x14000bda3  push    rsi
0x14000bda4  push    rdi
0x14000bda5  sub     rsp, 48h
0x14000bda9  mov     rax, [rcx+10h]
0x14000bdad  mov     rbp, rdx
0x14000bdb0  mov     [rsp+68h+arg_0], 0
0x14000bdb9  lea     rdx, [rsp+68h+arg_0]
0x14000bdbe  mov     [rsp+68h+var_38], 0
0x14000bdc7  mov     edi, r9d
0x14000bdca  mov     rsi, r8
0x14000bdcd  mov     rcx, [rax+270h]
0x14000bdd4  mov     rax, [rcx]
0x14000bdd7  mov     rax, [rax+80h]
0x14000bdde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bde3  mov     ebx, eax
0x14000bde5  test    eax, eax
0x14000bde7  js      short loc_14000BE32
0x14000bde9  mov     rcx, [rsp+68h+arg_0]
0x14000bdee  lea     r8, [rsp+68h+var_38]
0x14000bdf3  lea     rdx, ?IID_IWshRuntime@@3U_GUID@@B; _GUID const IID_IWshRuntime
0x14000bdfa  mov     rax, [rcx]
0x14000bdfd  mov     rax, [rax]
0x14000be00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000be05  mov     ebx, eax
0x14000be07  test    eax, eax
0x14000be09  js      short loc_14000BE32
0x14000be0b  mov     rcx, [rsp+68h+var_38]
0x14000be10  mov     r9d, edi
0x14000be13  mov     edx, [rsp+68h+arg_20]
0x14000be1a  mov     r8, rsi
0x14000be1d  mov     [rsp+68h+var_48], edx
0x14000be21  mov     rdx, rbp
0x14000be24  mov     rax, [rcx]
0x14000be27  mov     rax, [rax+18h]
0x14000be2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000be30  mov     ebx, eax
0x14000be32  mov     rcx, [rsp+68h+arg_0]
0x14000be37  test    rcx, rcx
0x14000be3a  jz      short loc_14000BE48
0x14000be3c  mov     rax, [rcx]
0x14000be3f  mov     rax, [rax+10h]
0x14000be43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000be48  mov     rcx, [rsp+68h+var_38]
0x14000be4d  test    rcx, rcx
0x14000be50  jz      short loc_14000BE5E
0x14000be52  mov     rax, [rcx]
0x14000be55  mov     rax, [rax+10h]
0x14000be59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000be5e  mov     eax, ebx
0x14000be60  add     rsp, 48h
0x14000be64  pop     rdi
0x14000be65  pop     rsi
0x14000be66  pop     rbp
0x14000be67  pop     rbx
0x14000be68  retn
```
