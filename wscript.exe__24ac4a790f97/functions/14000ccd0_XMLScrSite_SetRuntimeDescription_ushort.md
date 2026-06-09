# XMLScrSite::SetRuntimeDescription(ushort *)

- ea: `0x14000ccd0`
- end: `0x14000cd84`
- name: `?SetRuntimeDescription@XMLScrSite@@UEAAJPEAG@Z`
- size: `180`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000ccd0`
- `0x140018010`

## pseudocode

```c
__int64 __fastcall XMLScrSite::SetRuntimeDescription(XMLScrSite *this, unsigned __int16 *a2)
{
  __int64 v2; // rax
  int v4; // ebx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF
  __int64 v7; // [rsp+40h] [rbp+18h] BYREF

  v2 = *((_QWORD *)this + 2);
  v6 = 0;
  v7 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(v2 + 624) + 128LL))(*(_QWORD *)(v2 + 624), &v6);
  if ( v4 >= 0 )
  {
    v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v6)(v6, &IID_IWshRuntime, &v7);
    if ( v4 >= 0 )
      v4 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v7 + 48LL))(v7, a2);
  }
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000ccd0  mov     r11, rsp
0x14000ccd3  mov     [r11+10h], rbx
0x14000ccd7  push    rdi
0x14000ccd8  sub     rsp, 20h
0x14000ccdc  mov     rax, [rcx+10h]
0x14000cce0  mov     rdi, rdx
0x14000cce3  mov     qword ptr [r11+8], 0
0x14000cceb  lea     rdx, [r11+8]
0x14000ccef  mov     qword ptr [r11+18h], 0
0x14000ccf7  mov     rcx, [rax+270h]
0x14000ccfe  mov     rax, [rcx]
0x14000cd01  mov     rax, [rax+80h]
0x14000cd08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cd0d  mov     ebx, eax
0x14000cd0f  test    eax, eax
0x14000cd11  js      short loc_14000CD4B
0x14000cd13  mov     rcx, [rsp+28h+arg_0]
0x14000cd18  lea     r8, [rsp+28h+arg_10]
0x14000cd1d  lea     rdx, ?IID_IWshRuntime@@3U_GUID@@B; _GUID const IID_IWshRuntime
0x14000cd24  mov     rax, [rcx]
0x14000cd27  mov     rax, [rax]
0x14000cd2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cd2f  mov     ebx, eax
0x14000cd31  test    eax, eax
0x14000cd33  js      short loc_14000CD4B
0x14000cd35  mov     rcx, [rsp+28h+arg_10]
0x14000cd3a  mov     rdx, rdi
0x14000cd3d  mov     rax, [rcx]
0x14000cd40  mov     rax, [rax+30h]
0x14000cd44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cd49  mov     ebx, eax
0x14000cd4b  mov     rcx, [rsp+28h+arg_0]
0x14000cd50  test    rcx, rcx
0x14000cd53  jz      short loc_14000CD61
0x14000cd55  mov     rax, [rcx]
0x14000cd58  mov     rax, [rax+10h]
0x14000cd5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cd61  mov     rcx, [rsp+28h+arg_10]
0x14000cd66  test    rcx, rcx
0x14000cd69  jz      short loc_14000CD77
0x14000cd6b  mov     rax, [rcx]
0x14000cd6e  mov     rax, [rax+10h]
0x14000cd72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cd77  mov     eax, ebx
0x14000cd79  mov     rbx, [rsp+28h+arg_8]
0x14000cd7e  add     rsp, 20h
0x14000cd82  pop     rdi
0x14000cd83  retn
```
