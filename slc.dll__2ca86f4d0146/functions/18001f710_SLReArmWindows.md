# SLReArmWindows

- ea: `0x18001f710`
- end: `0x18001f777`
- name: `SLReArmWindows`
- size: `103`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18001d9c8`
- `0x18001e540`
- `0x18001f710`

## import_xrefs

- `sppc!SLOpen` at `0x18001f724`
- `sppc!SLOpen` at `0x18001f724`
- `sppc!SLReArm` at `0x18001f745`
- `sppc!SLReArm` at `0x18001f745`
- `sppc!SLClose` at `0x18001f769`
- `sppc!SLClose` at `0x18001f769`

## pseudocode

```c
__int64 SLReArmWindows()
{
  HRESULT v0; // eax
  unsigned int v1; // ebx
  HSLC phSLC; // [rsp+30h] [rbp+8h] BYREF

  phSLC = 0;
  v0 = SLOpen_0(&phSLC);
  v1 = v0;
  if ( v0 < 0 || (v0 = SLReArm(phSLC, &pApplicationId, 0, 1u), v1 = v0, v0 < 0) )
    sub_18001D9C8((unsigned int)v0);
  sub_18001E540(v1);
  if ( phSLC )
    SLClose_0(phSLC);
  return v1;
}

```

## disassembly

```asm
0x18001f710  push    rbx
0x18001f712  sub     rsp, 20h
0x18001f716  lea     rcx, [rsp+28h+phSLC]; phSLC
0x18001f71b  mov     [rsp+28h+phSLC], 0
0x18001f724  call    cs:SLOpen_0
0x18001f72a  mov     ebx, eax
0x18001f72c  test    eax, eax
0x18001f72e  js      short loc_18001F751
0x18001f730  mov     rcx, [rsp+28h+phSLC]; hSLC
0x18001f735  lea     rdx, pApplicationId; pApplicationId
0x18001f73c  mov     r9d, 1; dwFlags
0x18001f742  xor     r8d, r8d; pProductSkuId
0x18001f745  call    cs:SLReArm
0x18001f74b  mov     ebx, eax
0x18001f74d  test    eax, eax
0x18001f74f  jns     short loc_18001F758
0x18001f751  mov     ecx, eax
0x18001f753  call    sub_18001D9C8
0x18001f758  mov     ecx, ebx
0x18001f75a  call    sub_18001E540
0x18001f75f  mov     rcx, [rsp+28h+phSLC]; hSLC
0x18001f764  test    rcx, rcx
0x18001f767  jz      short loc_18001F76F
0x18001f769  call    cs:SLClose_0
0x18001f76f  mov     eax, ebx
0x18001f771  add     rsp, 20h
0x18001f775  pop     rbx
0x18001f776  retn
```
