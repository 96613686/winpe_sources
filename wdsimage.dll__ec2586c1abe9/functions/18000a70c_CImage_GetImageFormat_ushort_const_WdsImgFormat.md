# CImage::GetImageFormat(ushort const *,WdsImgFormat *)

- ea: `0x18000a70c`
- end: `0x18000a80b`
- name: `?GetImageFormat@CImage@@SAJPEBGPEAW4WdsImgFormat@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(const unsigned __int16 *, enum WdsImgFormat *)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006aa0`
- `0x18000ae64`
- `0x18000b108`
- `0x18000dbd0`

## callees

- `0x18000a70c`
- `0x18000d5b0`

## import_xrefs

- `WdsCommonLib!WdsIsValidFileExtension` at `0x18000a739`
- `WdsCommonLib!WdsIsValidFileExtension` at `0x18000a772`
- `WdsCommonLib!WdsIsValidFileExtension` at `0x18000a7a7`
- `WdsCommonLib!WdsIsValidFileExtension` at `0x18000a739`
- `WdsCommonLib!WdsIsValidFileExtension` at `0x18000a772`
- `WdsCommonLib!WdsIsValidFileExtension` at `0x18000a7a7`

## pseudocode

```c
__int64 __fastcall CImage::GetImageFormat(const unsigned __int16 *a1, enum WdsImgFormat *a2)
{
  __int64 IsValidFileExtension; // rdi
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx
  _DWORD v9[6]; // [rsp+20h] [rbp-18h] BYREF
  int v10; // [rsp+50h] [rbp+18h] BYREF
  int v11; // [rsp+58h] [rbp+20h] BYREF

  v10 = 0;
  v11 = 0;
  v9[0] = 0;
  IsValidFileExtension = (unsigned int)WdsIsValidFileExtension(a1, L"WIM", &v10);
  if ( (int)ElValidateHr_5(IsValidFileExtension, v5, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 3510) >= 0 )
  {
    IsValidFileExtension = (unsigned int)WdsIsValidFileExtension(a1, L"VHD", &v11);
    if ( (int)ElValidateHr_5(IsValidFileExtension, v6, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 3516) >= 0 )
    {
      LODWORD(IsValidFileExtension) = WdsIsValidFileExtension(a1, L"VHDX", v9);
      if ( (int)ElValidateHr_5((unsigned int)IsValidFileExtension, v7, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 3522) >= 0 )
      {
        if ( v10 )
        {
          *(_DWORD *)a2 = 2;
        }
        else if ( v11 )
        {
          *(_DWORD *)a2 = 1;
        }
        else
        {
          *(_DWORD *)a2 = v9[0] != 0 ? 3 : 0;
        }
      }
    }
  }
  return (unsigned int)IsValidFileExtension;
}

```

## disassembly

```asm
0x18000a70c  mov     rax, rsp
0x18000a70f  mov     [rax+8], rbx
0x18000a713  mov     [rax+10h], rsi
0x18000a717  push    rdi
0x18000a718  sub     rsp, 30h
0x18000a71c  and     dword ptr [rax+18h], 0
0x18000a720  lea     r8, [rax+18h]
0x18000a724  and     dword ptr [rax+20h], 0
0x18000a728  mov     rbx, rdx
0x18000a72b  and     dword ptr [rax-18h], 0
0x18000a72f  lea     rdx, aWim; "WIM"
0x18000a736  mov     rsi, rcx
0x18000a739  call    cs:__imp_WdsIsValidFileExtension
0x18000a740  nop     dword ptr [rax+rax+00h]
0x18000a745  mov     r9d, 0DB6h
0x18000a74b  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000a752  mov     ecx, eax
0x18000a754  mov     edi, eax
0x18000a756  call    ElValidateHr_5
0x18000a75b  test    eax, eax
0x18000a75d  js      loc_18000A7F8
0x18000a763  lea     r8, [rsp+38h+arg_18]
0x18000a768  mov     rcx, rsi
0x18000a76b  lea     rdx, aVhd; "VHD"
0x18000a772  call    cs:__imp_WdsIsValidFileExtension
0x18000a779  nop     dword ptr [rax+rax+00h]
0x18000a77e  mov     r9d, 0DBCh
0x18000a784  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000a78b  mov     ecx, eax
0x18000a78d  mov     edi, eax
0x18000a78f  call    ElValidateHr_5
0x18000a794  test    eax, eax
0x18000a796  js      short loc_18000A7F8
0x18000a798  lea     r8, [rsp+38h+var_18]
0x18000a79d  mov     rcx, rsi
0x18000a7a0  lea     rdx, aVhdx; "VHDX"
0x18000a7a7  call    cs:__imp_WdsIsValidFileExtension
0x18000a7ae  nop     dword ptr [rax+rax+00h]
0x18000a7b3  mov     r9d, 0DC2h
0x18000a7b9  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000a7c0  mov     ecx, eax
0x18000a7c2  mov     edi, eax
0x18000a7c4  call    ElValidateHr_5
0x18000a7c9  test    eax, eax
0x18000a7cb  js      short loc_18000A7F8
0x18000a7cd  cmp     [rsp+38h+arg_10], 0
0x18000a7d2  jz      short loc_18000A7DC
0x18000a7d4  mov     dword ptr [rbx], 2
0x18000a7da  jmp     short loc_18000A7F8
0x18000a7dc  cmp     [rsp+38h+arg_18], 0
0x18000a7e1  jz      short loc_18000A7EB
0x18000a7e3  mov     dword ptr [rbx], 1
0x18000a7e9  jmp     short loc_18000A7F8
0x18000a7eb  mov     eax, [rsp+38h+var_18]
0x18000a7ef  neg     eax
0x18000a7f1  sbb     ecx, ecx
0x18000a7f3  and     ecx, 3
0x18000a7f6  mov     [rbx], ecx
0x18000a7f8  mov     rbx, [rsp+38h+arg_0]
0x18000a7fd  mov     eax, edi
0x18000a7ff  mov     rsi, [rsp+38h+arg_8]
0x18000a804  add     rsp, 30h
0x18000a808  pop     rdi
0x18000a809  retn
```
