# CIconicBitmapRegistry::InvalidateBitmaps(CWindowData *,ulong)

- ea: `0x180065a6c`
- end: `0x180065b95`
- name: `?InvalidateBitmaps@CIconicBitmapRegistry@@QEAAJPEAVCWindowData@@K@Z`
- size: `297`
- prototype: `__int64 __fastcall(CIconicBitmapRegistry *__hidden this, struct CWindowData *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180065990`

## callees

- `0x18001a690`
- `0x18001ab0c`
- `0x18001f43c`
- `0x180042e9c`
- `0x180065a6c`

## import_xrefs

- `USER32!GetWindowThreadProcessId` at `0x180065a94`
- `USER32!GetWindowThreadProcessId` at `0x180065a94`

## pseudocode

```c
__int64 __fastcall CIconicBitmapRegistry::InvalidateBitmaps(CIconicBitmapRegistry *this, HWND *a2, int a3)
{
  unsigned int v6; // edi
  __int64 v7; // rax
  int v9; // r9d
  struct CWindowData *v10; // rdx
  int v11; // eax
  unsigned int v12; // [rsp+20h] [rbp-18h]
  DWORD v13; // [rsp+48h] [rbp+10h] BYREF

  v13 = 0;
  if ( !GetWindowThreadProcessId(a2[5], &v13) || a3 != v13 )
  {
    v6 = -2147024809;
    v9 = -2147024809;
    v12 = 813;
LABEL_7:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, (const int *const)"W", 1u, v9, v12, 0);
    return v6;
  }
  v6 = 0;
  if ( a2[54] && CIconicBitmapRegistry::CanAcceptBitmap(this, (struct CWindowData *)a2) )
  {
    *((_BYTE *)a2 + 738) &= 0xEBu;
    if ( a2[61] )
    {
      v11 = CIconicBitmapRegistry::RequestBitmap(this, v10, 1);
      v6 = v11;
      if ( v11 < 0 )
      {
        v12 = 824;
LABEL_12:
        v9 = v11;
        goto LABEL_7;
      }
    }
    else
    {
      CIconicBitmapRegistry::ClearBitmap(this, v10);
    }
  }
  v7 = *((_QWORD *)this + 12);
  if ( v7 )
  {
    if ( *(HWND **)(v7 + 72) == a2 && !*((_BYTE *)this + 89) )
    {
      *((_BYTE *)this + 90) = 0;
      v11 = CIconicBitmapRegistry::RequestBitmap(this, (struct CWindowData *)0xFFFFFFFFFFFFFFFFLL, 1);
      v6 = v11;
      if ( v11 < 0 )
      {
        v12 = 836;
        goto LABEL_12;
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180065a6c  mov     rax, rsp
0x180065a6f  mov     [rax+8], rbx
0x180065a73  mov     [rax+18h], rsi
0x180065a77  push    rdi
0x180065a78  sub     rsp, 30h
0x180065a7c  mov     rbx, rdx
0x180065a7f  mov     dword ptr [rax+10h], 0
0x180065a86  mov     rsi, rcx
0x180065a89  lea     rdx, [rax+10h]; lpdwProcessId
0x180065a8d  mov     edi, r8d
0x180065a90  mov     rcx, [rbx+28h]; hWnd
0x180065a94  call    cs:__imp_GetWindowThreadProcessId
0x180065a9a  test    eax, eax
0x180065a9c  jz      short loc_180065ACE
0x180065a9e  cmp     edi, [rsp+38h+arg_8]
0x180065aa2  jnz     short loc_180065ACE
0x180065aa4  xor     edi, edi
0x180065aa6  cmp     [rbx+1B0h], rdi
0x180065aad  jnz     short loc_180065AFF
0x180065aaf  mov     rax, [rsi+60h]
0x180065ab3  test    rax, rax
0x180065ab6  jnz     loc_180065B62
0x180065abc  mov     rbx, [rsp+38h+arg_0]
0x180065ac1  mov     eax, edi
0x180065ac3  mov     rsi, [rsp+38h+arg_10]
0x180065ac8  add     rsp, 30h
0x180065acc  pop     rdi
0x180065acd  retn
0x180065ace  mov     edi, 80070057h
0x180065ad3  mov     [rsp+38h+var_10], 0; void *
0x180065adc  mov     r9d, edi; int
0x180065adf  mov     [rsp+38h+var_18], 32Dh; unsigned int
0x180065ae7  mov     r8d, 1; unsigned int
0x180065aed  lea     rdx, aW; "W"
0x180065af4  lea     ecx, [r8+13h]; unsigned int
0x180065af8  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180065afd  jmp     short loc_180065ABC
0x180065aff  mov     rdx, rbx; struct CWindowData *
0x180065b02  mov     rcx, rsi; this
0x180065b05  call    ?CanAcceptBitmap@CIconicBitmapRegistry@@AEAA_NPEAVCWindowData@@@Z; CIconicBitmapRegistry::CanAcceptBitmap(CWindowData *)
0x180065b0a  test    al, al
0x180065b0c  jz      short loc_180065AAF
0x180065b0e  and     byte ptr [rbx+2E2h], 0EBh
0x180065b15  mov     rcx, rsi; this
0x180065b18  cmp     [rbx+1E8h], rdi
0x180065b1f  jz      short loc_180065B58
0x180065b21  mov     r8b, 1; bool
0x180065b24  call    ?RequestBitmap@CIconicBitmapRegistry@@AEAAJPEAVCWindowData@@_N@Z; CIconicBitmapRegistry::RequestBitmap(CWindowData *,bool)
0x180065b29  mov     edi, eax
0x180065b2b  test    eax, eax
0x180065b2d  jns     short loc_180065AAF
0x180065b2f  mov     [rsp+38h+var_10], 0
0x180065b38  mov     [rsp+38h+var_18], 338h
0x180065b40  jmp     short loc_180065B53
0x180065b42  mov     [rsp+38h+var_10], 0
0x180065b4b  mov     [rsp+38h+var_18], 344h
0x180065b53  mov     r9d, eax
0x180065b56  jmp     short loc_180065AE7
0x180065b58  call    ?ClearBitmap@CIconicBitmapRegistry@@AEAAXPEAVCWindowData@@@Z; CIconicBitmapRegistry::ClearBitmap(CWindowData *)
0x180065b5d  jmp     loc_180065AAF
0x180065b62  cmp     [rax+48h], rbx
0x180065b66  jnz     loc_180065ABC
0x180065b6c  cmp     byte ptr [rsi+59h], 0
0x180065b70  jnz     loc_180065ABC
0x180065b76  mov     r8b, 1; bool
0x180065b79  mov     byte ptr [rsi+5Ah], 0
0x180065b7d  or      rdx, 0FFFFFFFFFFFFFFFFh; struct CWindowData *
0x180065b81  mov     rcx, rsi; this
0x180065b84  call    ?RequestBitmap@CIconicBitmapRegistry@@AEAAJPEAVCWindowData@@_N@Z; CIconicBitmapRegistry::RequestBitmap(CWindowData *,bool)
0x180065b89  mov     edi, eax
0x180065b8b  test    eax, eax
0x180065b8d  jns     loc_180065ABC
0x180065b93  jmp     short loc_180065B42
```
