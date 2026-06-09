# XMLScrSite::AddRuntimeUnnamed(ushort *,ushort *,int,ulong)

- ea: `0x14000be70`
- end: `0x14000bf39`
- name: `?AddRuntimeUnnamed@XMLScrSite@@UEAAJPEAG0HK@Z`
- size: `201`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this, unsigned __int16 *, unsigned __int16 *, int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000be70`
- `0x140018010`

## pseudocode

```c
__int64 __fastcall XMLScrSite::AddRuntimeUnnamed(
        XMLScrSite *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5)
{
  __int64 v5; // rax
  int v9; // ebx
  _QWORD v11[7]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v12; // [rsp+70h] [rbp+8h] BYREF

  v5 = *((_QWORD *)this + 2);
  v12 = 0;
  v11[0] = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(v5 + 624) + 128LL))(*(_QWORD *)(v5 + 624), &v12);
  if ( v9 >= 0 )
  {
    v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v12)(v12, &IID_IWshRuntime, v11);
    if ( v9 >= 0 )
      v9 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, unsigned __int16 *, _QWORD, unsigned int))(*(_QWORD *)v11[0] + 32LL))(
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
0x14000be70  push    rbx
0x14000be72  push    rbp
0x14000be73  push    rsi
0x14000be74  push    rdi
0x14000be75  sub     rsp, 48h
0x14000be79  mov     rax, [rcx+10h]
0x14000be7d  mov     rbp, rdx
0x14000be80  mov     [rsp+68h+arg_0], 0
0x14000be89  lea     rdx, [rsp+68h+arg_0]
0x14000be8e  mov     [rsp+68h+var_38], 0
0x14000be97  mov     edi, r9d
0x14000be9a  mov     rsi, r8
0x14000be9d  mov     rcx, [rax+270h]
0x14000bea4  mov     rax, [rcx]
0x14000bea7  mov     rax, [rax+80h]
0x14000beae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000beb3  mov     ebx, eax
0x14000beb5  test    eax, eax
0x14000beb7  js      short loc_14000BF02
0x14000beb9  mov     rcx, [rsp+68h+arg_0]
0x14000bebe  lea     r8, [rsp+68h+var_38]
0x14000bec3  lea     rdx, ?IID_IWshRuntime@@3U_GUID@@B; _GUID const IID_IWshRuntime
0x14000beca  mov     rax, [rcx]
0x14000becd  mov     rax, [rax]
0x14000bed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bed5  mov     ebx, eax
0x14000bed7  test    eax, eax
0x14000bed9  js      short loc_14000BF02
0x14000bedb  mov     rcx, [rsp+68h+var_38]
0x14000bee0  mov     r9d, edi
0x14000bee3  mov     edx, [rsp+68h+arg_20]
0x14000beea  mov     r8, rsi
0x14000beed  mov     [rsp+68h+var_48], edx
0x14000bef1  mov     rdx, rbp
0x14000bef4  mov     rax, [rcx]
0x14000bef7  mov     rax, [rax+20h]
0x14000befb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bf00  mov     ebx, eax
0x14000bf02  mov     rcx, [rsp+68h+arg_0]
0x14000bf07  test    rcx, rcx
0x14000bf0a  jz      short loc_14000BF18
0x14000bf0c  mov     rax, [rcx]
0x14000bf0f  mov     rax, [rax+10h]
0x14000bf13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bf18  mov     rcx, [rsp+68h+var_38]
0x14000bf1d  test    rcx, rcx
0x14000bf20  jz      short loc_14000BF2E
0x14000bf22  mov     rax, [rcx]
0x14000bf25  mov     rax, [rax+10h]
0x14000bf29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bf2e  mov     eax, ebx
0x14000bf30  add     rsp, 48h
0x14000bf34  pop     rdi
0x14000bf35  pop     rsi
0x14000bf36  pop     rbp
0x14000bf37  pop     rbx
0x14000bf38  retn
```
