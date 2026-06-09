# CElevateWlanUi::GetProfileKey(ushort const *,_GUID *,ulong *,ushort * *)

- ea: `0x180011680`
- end: `0x180011710`
- name: `?GetProfileKey@CElevateWlanUi@@UEAAJPEBGPEAU_GUID@@PEAKPEAPEAG@Z`
- size: `144`
- prototype: `__int64 __fastcall(CElevateWlanUi *this, const unsigned __int16 *, struct _GUID *, unsigned int *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180006588`
- `0x180011680`

## import_xrefs

- `wlanapi!WlanOpenHandle` at `0x1800116b0`
- `wlanapi!WlanOpenHandle` at `0x1800116b0`
- `wlanapi!WlanCloseHandle` at `0x1800116ff`
- `wlanapi!WlanCloseHandle` at `0x1800116ff`

## pseudocode

```c
__int64 __fastcall CElevateWlanUi::GetProfileKey(
        CElevateWlanUi *this,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        unsigned int *a4,
        unsigned __int16 **a5)
{
  signed int v8; // eax
  signed int v9; // ebx
  int v10; // eax
  DWORD v12; // [rsp+30h] [rbp-38h] BYREF
  HANDLE hClientHandle; // [rsp+38h] [rbp-30h] BYREF

  v12 = 0;
  hClientHandle = 0;
  v8 = WlanOpenHandle(2u, 0, &v12, &hClientHandle);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 >= 0 )
  {
    v10 = WLUIGetProfileKey(hClientHandle, a2, a3, a4, a5);
    v9 = v10;
    if ( v10 > 0 )
      v9 = (unsigned __int16)v10 | 0x80070000;
    WlanCloseHandle(hClientHandle, 0);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180011680  mov     rax, rsp
0x180011683  push    rbx
0x180011684  push    rbp
0x180011685  push    rsi
0x180011686  push    rdi
0x180011687  sub     rsp, 48h
0x18001168b  mov     rbp, rdx
0x18001168e  mov     dword ptr [rax-38h], 0
0x180011695  xor     edx, edx; pReserved
0x180011697  mov     qword ptr [rax-30h], 0
0x18001169f  mov     rdi, r9
0x1800116a2  mov     rsi, r8
0x1800116a5  lea     r9, [rax-30h]; phClientHandle
0x1800116a9  lea     r8, [rax-38h]; pdwNegotiatedVersion
0x1800116ad  lea     ecx, [rdx+2]; dwClientVersion
0x1800116b0  call    cs:__imp_WlanOpenHandle
0x1800116b6  mov     ebx, eax
0x1800116b8  test    eax, eax
0x1800116ba  jle     short loc_1800116C5
0x1800116bc  movzx   ebx, ax
0x1800116bf  or      ebx, 80070000h
0x1800116c5  test    ebx, ebx
0x1800116c7  js      short loc_180011705
0x1800116c9  mov     rax, [rsp+68h+arg_20]
0x1800116d1  mov     r9, rdi; unsigned int *
0x1800116d4  mov     rcx, [rsp+68h+hClientHandle]; void *
0x1800116d9  mov     r8, rsi; struct _GUID *
0x1800116dc  mov     rdx, rbp; unsigned __int16 *
0x1800116df  mov     [rsp+68h+var_48], rax; unsigned __int16 **
0x1800116e4  call    ?WLUIGetProfileKey@@YAKPEAXPEBGPEAU_GUID@@PEAKPEAPEAG@Z; WLUIGetProfileKey(void *,ushort const *,_GUID *,ulong *,ushort * *)
0x1800116e9  mov     ebx, eax
0x1800116eb  test    eax, eax
0x1800116ed  jle     short loc_1800116F8
0x1800116ef  movzx   ebx, ax
0x1800116f2  or      ebx, 80070000h
0x1800116f8  mov     rcx, [rsp+68h+hClientHandle]; hClientHandle
0x1800116fd  xor     edx, edx; pReserved
0x1800116ff  call    cs:__imp_WlanCloseHandle
0x180011705  mov     eax, ebx
0x180011707  add     rsp, 48h
0x18001170b  pop     rdi
0x18001170c  pop     rsi
0x18001170d  pop     rbp
0x18001170e  pop     rbx
0x18001170f  retn
```
