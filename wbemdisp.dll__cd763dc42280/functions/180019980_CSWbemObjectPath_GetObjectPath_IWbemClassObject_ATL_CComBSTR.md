# CSWbemObjectPath::GetObjectPath(IWbemClassObject *,ATL::CComBSTR &)

- ea: `0x180019980`
- end: `0x180019a2c`
- name: `?GetObjectPath@CSWbemObjectPath@@SA_NPEAUIWbemClassObject@@AEAVCComBSTR@ATL@@@Z`
- size: `172`
- prototype: `bool __fastcall(struct IWbemClassObject *, struct ATL::CComBSTR *)`
- caller_count: `13`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180019510`
- `0x18002a840`
- `0x18002a990`
- `0x18002aa50`
- `0x18002ab30`
- `0x18002af00`
- `0x18002b020`
- `0x18002b310`
- `0x18002b3a0`
- `0x18002b770`
- `0x18002bc50`
- `0x18002bd60`
- `0x18002c460`

## callees

- `0x180017ce0`
- `0x180019980`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180019a1b`
- `OLEAUT32!__imp_VariantClear` at `0x180019a1b`

## string_xrefs

- `0x1800199c1`: `__RELPATH`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall CSWbemObjectPath::GetObjectPath(struct IWbemClassObject *a1, struct ATL::CComBSTR *a2)
{
  char v3; // bl
  __int64 v4; // rax
  VARIANTARG pvarg; // [rsp+40h] [rbp-48h] BYREF

  v3 = 0;
  if ( a1 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    pvarg.vt = 0;
    if ( ((int (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a1->lpVtbl->Get)(
           a1,
           L"__RELPATH",
           0,
           &pvarg,
           0,
           0) >= 0
      && pvarg.vt == 8 )
    {
      if ( pvarg.llVal )
      {
        v4 = -1;
        do
          ++v4;
        while ( *(_WORD *)(pvarg.llVal + 2 * v4) );
        if ( v4 )
        {
          ATL::CComBSTR::operator=(a2);
          v3 = 1;
        }
      }
    }
    if ( pvarg.vt == 4095 )
      pvarg.vt = 8;
    VariantClear(&pvarg);
  }
  return v3;
}

```

## disassembly

```asm
0x180019980  mov     r11, rsp
0x180019983  push    rbx
0x180019984  push    rbp
0x180019985  push    rsi
0x180019986  push    rdi
0x180019987  sub     rsp, 68h
0x18001998b  mov     rdi, rdx
0x18001998e  xor     esi, esi
0x180019990  mov     bl, sil
0x180019993  test    rcx, rcx
0x180019996  jz      loc_180019A21
0x18001999c  xorps   xmm0, xmm0
0x18001999f  xor     eax, eax
0x1800199a1  movups  xmmword ptr [rsp+88h+pvarg], xmm0
0x1800199a6  mov     [r11-38h], rax
0x1800199aa  mov     word ptr [rsp+88h+pvarg], si
0x1800199af  mov     rax, [rcx]
0x1800199b2  mov     [r11-60h], rsi
0x1800199b6  mov     [r11-68h], rsi
0x1800199ba  lea     r9, [r11-48h]
0x1800199be  xor     r8d, r8d
0x1800199c1  lea     rdx, aRelpath; "__RELPATH"
0x1800199c8  mov     rax, [rax+20h]
0x1800199cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199d1  lea     ebp, [rsi+8]
0x1800199d4  test    eax, eax
0x1800199d6  js      short loc_180019A05
0x1800199d8  cmp     bp, word ptr [rsp+88h+pvarg]
0x1800199dd  jnz     short loc_180019A05
0x1800199df  mov     rdx, qword ptr [rsp+88h+pvarg+8]
0x1800199e4  test    rdx, rdx
0x1800199e7  jz      short loc_180019A05
0x1800199e9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800199ed  inc     rax
0x1800199f0  cmp     [rdx+rax*2], si
0x1800199f4  jnz     short loc_1800199ED
0x1800199f6  test    rax, rax
0x1800199f9  jz      short loc_180019A05
0x1800199fb  mov     rcx, rdi
0x1800199fe  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180019a03  mov     bl, 1
0x180019a05  mov     eax, 0FFFh
0x180019a0a  cmp     word ptr [rsp+88h+pvarg], ax
0x180019a0f  jnz     short loc_180019A16
0x180019a11  mov     word ptr [rsp+88h+pvarg], bp
0x180019a16  lea     rcx, [rsp+88h+pvarg]; pvarg
0x180019a1b  call    cs:__imp_VariantClear
0x180019a21  mov     al, bl
0x180019a23  add     rsp, 68h
0x180019a27  pop     rdi
0x180019a28  pop     rsi
0x180019a29  pop     rbp
0x180019a2a  pop     rbx
0x180019a2b  retn
```
