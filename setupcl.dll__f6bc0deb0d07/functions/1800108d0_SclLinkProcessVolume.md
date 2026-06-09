# SclLinkProcessVolume

- ea: `0x1800108d0`
- end: `0x1800109e7`
- name: `SclLinkProcessVolume`
- size: `279`
- prototype: `__int64 __fastcall(__int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800065f8`

## callees

- `0x18000a524`
- `0x18000e740`
- `0x1800108d0`
- `0x180016340`

## import_xrefs

- `ntdll!NtClose` at `0x1800109ca`
- `ntdll!NtClose` at `0x1800109ca`

## string_xrefs

- `0x180010921`: `Processing links on volume [%ws]: old base = [%ws]; new base = [%ws]`
- `0x180010905`: `SclLinkProcessVolume`
- `0x1800109a3`: `(%lx): Failed to enumerate reparse points on volume [%ws]`

## pseudocode

```c
__int64 __fastcall SclLinkProcessVolume(__int64 a1, const WCHAR *a2)
{
  int v2; // esi
  int VolumeHandle; // ebx
  int v6; // r8d
  int v7; // r9d
  HANDLE Handle; // [rsp+70h] [rbp+8h] BYREF
  int v10; // [rsp+80h] [rbp+18h] BYREF
  int v11; // [rsp+84h] [rbp+1Ch]

  Handle = 0;
  v2 = a1 + 1152;
  if ( !a1 )
    v2 = 0;
  SclLogGenericMessage(v2, 1, (unsigned int)SclEvent_Generic_Info, 70, (__int64)"SclLinkProcessVolume");
  VolumeHandle = SclGetVolumeHandle(a2, &Handle);
  if ( VolumeHandle >= 0 )
  {
    v10 = -1610612733;
    v11 = -1610612724;
    VolumeHandle = WdsEnumVolumeReparsePointsByHandle((_DWORD)Handle, (unsigned int)&v10, v6, v7, a1);
    if ( VolumeHandle < 0 )
      SclLogGenericMessage(v2, 3, (unsigned int)SclEvent_Generic_Error, 93, (__int64)"SclLinkProcessVolume");
  }
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)VolumeHandle;
}

```

## disassembly

```asm
0x1800108d0  mov     r11, rsp
0x1800108d3  mov     [r11+10h], rbx
0x1800108d7  mov     [r11+20h], rbp
0x1800108db  push    rsi
0x1800108dc  push    rdi
0x1800108dd  push    r14
0x1800108df  sub     rsp, 50h
0x1800108e3  xor     eax, eax
0x1800108e5  mov     qword ptr [r11+8], 0
0x1800108ed  lea     r8, [rcx+20h]
0x1800108f1  test    rcx, rcx
0x1800108f4  lea     rsi, [rcx+480h]
0x1800108fb  mov     r9d, 46h ; 'F'
0x180010901  cmovz   rsi, rax
0x180010905  lea     r14, aScllinkprocess; "SclLinkProcessVolume"
0x18001090c  lea     rax, [rcx+228h]
0x180010913  mov     rbp, rdx
0x180010916  mov     [r11-28h], rax
0x18001091a  mov     rdi, rcx
0x18001091d  mov     [r11-30h], r8
0x180010921  lea     rax, aProcessingLink; "Processing links on volume [%ws]: old b"...
0x180010928  mov     [r11-38h], rdx
0x18001092c  lea     r8, SclEvent_Generic_Info
0x180010933  mov     [r11-40h], rax
0x180010937  lea     edx, [r9-45h]
0x18001093b  mov     rcx, rsi
0x18001093e  mov     [r11-48h], r14
0x180010942  call    SclLogGenericMessage
0x180010947  lea     rdx, [rsp+68h+Handle]
0x18001094c  mov     rcx, rbp
0x18001094f  call    SclGetVolumeHandle
0x180010954  mov     ebx, eax
0x180010956  test    eax, eax
0x180010958  js      short loc_1800109C0
0x18001095a  mov     rcx, [rsp+68h+Handle]
0x18001095f  lea     rdx, [rsp+68h+arg_10]
0x180010967  mov     [rsp+68h+arg_10], 0A0000003h
0x180010972  mov     [rsp+68h+arg_14], 0A000000Ch
0x18001097d  mov     [rsp+68h+var_48], rdi
0x180010982  call    WdsEnumVolumeReparsePointsByHandle
0x180010987  mov     ebx, eax
0x180010989  test    eax, eax
0x18001098b  jns     short loc_1800109C0
0x18001098d  mov     [rsp+68h+var_30], rbp
0x180010992  lea     r8, SclEvent_Generic_Error
0x180010999  mov     [rsp+68h+var_38], eax
0x18001099d  mov     r9d, 5Dh ; ']'
0x1800109a3  lea     rax, aLxFailedToEnum_0; "(%lx): Failed to enumerate reparse poin"...
0x1800109aa  mov     rcx, rsi
0x1800109ad  mov     [rsp+68h+var_40], rax
0x1800109b2  mov     [rsp+68h+var_48], r14
0x1800109b7  lea     edx, [r9-5Ah]
0x1800109bb  call    SclLogGenericMessage
0x1800109c0  mov     rcx, [rsp+68h+Handle]; Handle
0x1800109c5  test    rcx, rcx
0x1800109c8  jz      short loc_1800109D0
0x1800109ca  call    cs:__imp_NtClose
0x1800109d0  lea     r11, [rsp+68h+var_18]
0x1800109d5  mov     eax, ebx
0x1800109d7  mov     rbx, [r11+28h]
0x1800109db  mov     rbp, [r11+38h]
0x1800109df  mov     rsp, r11
0x1800109e2  pop     r14
0x1800109e4  pop     rdi
0x1800109e5  pop     rsi
0x1800109e6  retn
```
