# BbCountValues(_BLACKBOARD *,ushort const *)

- ea: `0x180008844`
- end: `0x180008923`
- name: `?BbCountValues@@YAIPEAU_BLACKBOARD@@PEBG@Z`
- size: `223`
- prototype: `unsigned int(struct _BLACKBOARD *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002898`
- `0x1800031a4`

## callees

- `0x180008844`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180008909`
- `KERNEL32!SetLastError` at `0x180008909`
- `KERNEL32!CompareStringW` at `0x1800088c7`
- `KERNEL32!CompareStringW` at `0x1800088c7`
- `WDSCORE!WdsEnumFirstBlackboardItem` at `0x180008893`
- `WDSCORE!WdsEnumFirstBlackboardItem` at `0x180008893`
- `WDSCORE!WdsAbortBlackboardItemEnum` at `0x1800088f4`
- `WDSCORE!WdsAbortBlackboardItemEnum` at `0x1800088f4`
- `WDSCORE!WdsEnumNextBlackboardItem` at `0x1800088df`
- `WDSCORE!WdsEnumNextBlackboardItem` at `0x1800088df`

## pseudocode

```c
__int64 __fastcall BbCountValues(struct _BLACKBOARD *a1, const unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  PCNZWCH lpString1[2]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v6; // [rsp+40h] [rbp-28h]
  __int64 v7; // [rsp+50h] [rbp-18h]

  v7 = 0;
  *(_OWORD *)lpString1 = 0;
  v6 = 0;
  if ( a1 && a2 )
  {
    v3 = 0;
    if ( (unsigned int)WdsEnumFirstBlackboardItem(lpString1, a1, a2, L"*", 2) )
    {
      do
      {
        if ( lpString1[1] )
        {
          if ( CompareStringW(0x409u, 1u, lpString1[1], -1, a2, -1) == 2 )
            ++v3;
        }
      }
      while ( (unsigned int)WdsEnumNextBlackboardItem(lpString1) );
      WdsAbortBlackboardItemEnum(lpString1);
    }
    return v3;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x180008844  mov     [rsp+arg_0], rbx
0x180008849  push    rdi
0x18000884a  sub     rsp, 60h
0x18000884e  xor     eax, eax
0x180008850  xorps   xmm0, xmm0
0x180008853  mov     [rsp+68h+var_18], rax
0x180008858  mov     rdi, rdx
0x18000885b  movups  xmmword ptr [rsp+68h+lpString1], xmm0
0x180008860  movups  [rsp+68h+var_28], xmm0
0x180008865  test    rcx, rcx
0x180008868  jz      loc_180008904
0x18000886e  test    rdx, rdx
0x180008871  jz      loc_180008904
0x180008877  mov     r8, rdx
0x18000887a  mov     dword ptr [rsp+68h+lpString2], 2
0x180008882  mov     rdx, rcx
0x180008885  lea     r9, asc_18003A218; "*"
0x18000888c  lea     rcx, [rsp+68h+lpString1]
0x180008891  xor     ebx, ebx
0x180008893  call    cs:__imp_WdsEnumFirstBlackboardItem
0x18000889a  nop     dword ptr [rax+rax+00h]
0x18000889f  test    eax, eax
0x1800088a1  jz      short loc_180008900
0x1800088a3  mov     r8, [rsp+68h+lpString1+8]; lpString1
0x1800088a8  test    r8, r8
0x1800088ab  jz      short loc_1800088DA
0x1800088ad  or      r9d, 0FFFFFFFFh; cchCount1
0x1800088b1  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800088b9  mov     ecx, 409h; Locale
0x1800088be  mov     [rsp+68h+lpString2], rdi; lpString2
0x1800088c3  lea     edx, [r9+2]; dwCmpFlags
0x1800088c7  call    cs:__imp_CompareStringW
0x1800088ce  nop     dword ptr [rax+rax+00h]
0x1800088d3  cmp     eax, 2
0x1800088d6  jnz     short loc_1800088DA
0x1800088d8  inc     ebx
0x1800088da  lea     rcx, [rsp+68h+lpString1]
0x1800088df  call    cs:__imp_WdsEnumNextBlackboardItem
0x1800088e6  nop     dword ptr [rax+rax+00h]
0x1800088eb  test    eax, eax
0x1800088ed  jnz     short loc_1800088A3
0x1800088ef  lea     rcx, [rsp+68h+lpString1]
0x1800088f4  call    cs:__imp_WdsAbortBlackboardItemEnum
0x1800088fb  nop     dword ptr [rax+rax+00h]
0x180008900  mov     eax, ebx
0x180008902  jmp     short loc_180008917
0x180008904  mov     ecx, 57h ; 'W'; dwErrCode
0x180008909  call    cs:__imp_SetLastError
0x180008910  nop     dword ptr [rax+rax+00h]
0x180008915  xor     eax, eax
0x180008917  mov     rbx, [rsp+68h+arg_0]
0x18000891c  add     rsp, 60h
0x180008920  pop     rdi
0x180008921  retn
```
