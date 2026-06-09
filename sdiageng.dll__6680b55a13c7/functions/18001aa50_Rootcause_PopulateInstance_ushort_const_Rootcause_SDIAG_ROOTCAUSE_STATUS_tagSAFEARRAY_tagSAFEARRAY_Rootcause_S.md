# Rootcause::PopulateInstance(ushort const *,Rootcause::SDIAG_ROOTCAUSE_STATUS,tagSAFEARRAY *,tagSAFEARRAY *,Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *)

- ea: `0x18001aa50`
- end: `0x18001aaea`
- name: `?PopulateInstance@Rootcause@@AEAAJPEBGW4SDIAG_ROOTCAUSE_STATUS@1@PEAUtagSAFEARRAY@@2PEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z`
- size: `154`
- prototype: `__int64 __fastcall(__int64, const OLECHAR *, int, SAFEARRAY *, SAFEARRAY *psa, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180019b88`
- `0x18001b4d4`

## callees

- `0x18001aa50`
- `0x180026fa0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001aa62`
- `OLEAUT32!__imp_SysAllocString` at `0x18001aa62`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18001aa97`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18001aab9`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18001aa97`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18001aab9`

## pseudocode

```c
__int64 __fastcall Rootcause::PopulateInstance(
        __int64 a1,
        const OLECHAR *a2,
        int a3,
        SAFEARRAY *a4,
        SAFEARRAY *psa,
        __int64 a6)
{
  BSTR v8; // rax
  unsigned int v9; // ebx
  int v10; // r8d
  int v11; // r9d
  HRESULT v12; // eax

  v8 = SysAllocString(a2);
  *(_QWORD *)(a6 + 16) = v8;
  if ( !v8 )
  {
    v9 = -2147024882;
    v10 = 2054;
    v11 = -2147024882;
LABEL_10:
    SdpDebugTrace(1u, L"Rootcause::PopulateInstance", v10, v11);
    return v9;
  }
  v9 = 0;
  *(_DWORD *)(a6 + 24) = a3;
  if ( a4 )
  {
    v12 = SafeArrayCopy(a4, (SAFEARRAY **)(a6 + 32));
    v9 = v12;
    if ( v12 < 0 )
    {
      v10 = 2060;
LABEL_9:
      v11 = v12;
      goto LABEL_10;
    }
  }
  if ( psa )
  {
    v12 = SafeArrayCopy(psa, (SAFEARRAY **)(a6 + 40));
    v9 = v12;
    if ( v12 < 0 )
    {
      v10 = 2065;
      goto LABEL_9;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18001aa50  push    rbx
0x18001aa52  push    rbp
0x18001aa53  push    rsi
0x18001aa54  push    rdi
0x18001aa55  sub     rsp, 28h
0x18001aa59  mov     rcx, rdx; psz
0x18001aa5c  mov     rsi, r9
0x18001aa5f  mov     ebp, r8d
0x18001aa62  call    cs:__imp_SysAllocString
0x18001aa68  mov     rdi, [rsp+48h+arg_28]
0x18001aa6d  mov     [rdi+10h], rax
0x18001aa71  test    rax, rax
0x18001aa74  jnz     short loc_18001AA86
0x18001aa76  mov     ebx, 8007000Eh
0x18001aa7b  mov     r8d, 806h
0x18001aa81  mov     r9d, ebx
0x18001aa84  jmp     short loc_18001AACE
0x18001aa86  xor     ebx, ebx
0x18001aa88  mov     [rdi+18h], ebp
0x18001aa8b  test    rsi, rsi
0x18001aa8e  jz      short loc_18001AAAB
0x18001aa90  lea     rdx, [rdi+20h]; ppsaOut
0x18001aa94  mov     rcx, rsi; psa
0x18001aa97  call    cs:__imp_SafeArrayCopy
0x18001aa9d  mov     ebx, eax
0x18001aa9f  test    eax, eax
0x18001aaa1  jns     short loc_18001AAAB
0x18001aaa3  mov     r8d, 80Ch
0x18001aaa9  jmp     short loc_18001AACB
0x18001aaab  mov     rcx, [rsp+48h+psa]; psa
0x18001aab0  test    rcx, rcx
0x18001aab3  jz      short loc_18001AADF
0x18001aab5  lea     rdx, [rdi+28h]; ppsaOut
0x18001aab9  call    cs:__imp_SafeArrayCopy
0x18001aabf  mov     ebx, eax
0x18001aac1  test    eax, eax
0x18001aac3  jns     short loc_18001AADF
0x18001aac5  mov     r8d, 811h; int
0x18001aacb  mov     r9d, eax; int
0x18001aace  lea     rdx, aRootcausePopul; "Rootcause::PopulateInstance"
0x18001aad5  mov     ecx, 1; Level
0x18001aada  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001aadf  mov     eax, ebx
0x18001aae1  add     rsp, 28h
0x18001aae5  pop     rdi
0x18001aae6  pop     rsi
0x18001aae7  pop     rbp
0x18001aae8  pop     rbx
0x18001aae9  retn
```
