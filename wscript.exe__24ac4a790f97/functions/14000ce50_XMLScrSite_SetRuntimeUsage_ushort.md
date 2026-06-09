# XMLScrSite::SetRuntimeUsage(ushort *)

- ea: `0x14000ce50`
- end: `0x14000cf04`
- name: `?SetRuntimeUsage@XMLScrSite@@UEAAJPEAG@Z`
- size: `180`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000ce50`
- `0x140018010`

## pseudocode

```c
__int64 __fastcall XMLScrSite::SetRuntimeUsage(XMLScrSite *this, unsigned __int16 *a2)
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
      v4 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v7 + 40LL))(v7, a2);
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
0x14000ce50  mov     r11, rsp
0x14000ce53  mov     [r11+10h], rbx
0x14000ce57  push    rdi
0x14000ce58  sub     rsp, 20h
0x14000ce5c  mov     rax, [rcx+10h]
0x14000ce60  mov     rdi, rdx
0x14000ce63  mov     qword ptr [r11+8], 0
0x14000ce6b  lea     rdx, [r11+8]
0x14000ce6f  mov     qword ptr [r11+18h], 0
0x14000ce77  mov     rcx, [rax+270h]
0x14000ce7e  mov     rax, [rcx]
0x14000ce81  mov     rax, [rax+80h]
0x14000ce88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ce8d  mov     ebx, eax
0x14000ce8f  test    eax, eax
0x14000ce91  js      short loc_14000CECB
0x14000ce93  mov     rcx, [rsp+28h+arg_0]
0x14000ce98  lea     r8, [rsp+28h+arg_10]
0x14000ce9d  lea     rdx, ?IID_IWshRuntime@@3U_GUID@@B; _GUID const IID_IWshRuntime
0x14000cea4  mov     rax, [rcx]
0x14000cea7  mov     rax, [rax]
0x14000ceaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ceaf  mov     ebx, eax
0x14000ceb1  test    eax, eax
0x14000ceb3  js      short loc_14000CECB
0x14000ceb5  mov     rcx, [rsp+28h+arg_10]
0x14000ceba  mov     rdx, rdi
0x14000cebd  mov     rax, [rcx]
0x14000cec0  mov     rax, [rax+28h]
0x14000cec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cec9  mov     ebx, eax
0x14000cecb  mov     rcx, [rsp+28h+arg_0]
0x14000ced0  test    rcx, rcx
0x14000ced3  jz      short loc_14000CEE1
0x14000ced5  mov     rax, [rcx]
0x14000ced8  mov     rax, [rax+10h]
0x14000cedc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cee1  mov     rcx, [rsp+28h+arg_10]
0x14000cee6  test    rcx, rcx
0x14000cee9  jz      short loc_14000CEF7
0x14000ceeb  mov     rax, [rcx]
0x14000ceee  mov     rax, [rax+10h]
0x14000cef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cef7  mov     eax, ebx
0x14000cef9  mov     rbx, [rsp+28h+arg_8]
0x14000cefe  add     rsp, 20h
0x14000cf02  pop     rdi
0x14000cf03  retn
```
