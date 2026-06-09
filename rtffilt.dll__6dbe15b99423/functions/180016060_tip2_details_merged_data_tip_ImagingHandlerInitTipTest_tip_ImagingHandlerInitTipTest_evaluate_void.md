# tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>::evaluate(void)

- ea: `0x180016060`
- end: `0x1800160fc`
- name: `?evaluate@?$merged_data@U_tip_ImagingHandlerInitTipTest@@U1@@details@tip2@@EEAAXXZ`
- size: `156`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180016060`

## string_xrefs

- `0x18001606c`: `reason::FailedToCoCreateWICImagingFactory`

## pseudocode

```c
const char *__fastcall tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>::evaluate(
        __int64 a1)
{
  const char *result; // rax
  char v2; // dl
  const char *v3; // r8
  __int64 v4; // rcx

  if ( *(_BYTE *)(a1 + 304) )
  {
    result = *(const char **)(a1 + 264);
    if ( (*((_DWORD *)result + 14) & 0x200) != 0 )
    {
      if ( result[152] )
        return result;
      *((_BYTE *)result + 152) = 1;
      *((_WORD *)result + 77) = 0x8000;
    }
    else
    {
      if ( result[152] )
        return result;
      *((_BYTE *)result + 152) = 3;
      *((_WORD *)result + 77) = 16385;
    }
    *((_QWORD *)result + 20) = 0;
  }
  else
  {
    result = "reason::FailedToCoCreateWICImagingFactory";
    v2 = 114;
    v3 = "reason::FailedToCoCreateWICImagingFactory";
    do
    {
      ++result;
      if ( v2 == 58 )
        v3 = result;
      v2 = *result;
    }
    while ( *result );
    v4 = *(_QWORD *)(a1 + 264);
    if ( !*(_BYTE *)(v4 + 152) )
    {
      *(_BYTE *)(v4 + 152) = 3;
      *(_WORD *)(v4 + 154) = 0;
      *(_QWORD *)(v4 + 160) = v3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180016060  xor     r9d, r9d
0x180016063  cmp     [rcx+130h], r9b
0x18001606a  jnz     short loc_1800160B0
0x18001606c  lea     rax, aReasonFailedto_1; "reason::FailedToCoCreateWICImagingFacto"...
0x180016073  mov     dl, 72h ; 'r'
0x180016075  mov     r8, rax
0x180016078  inc     rax
0x18001607b  cmp     dl, 3Ah ; ':'
0x18001607e  jnz     short loc_180016083
0x180016080  mov     r8, rax
0x180016083  mov     dl, [rax]
0x180016085  test    dl, dl
0x180016087  jnz     short loc_180016078
0x180016089  mov     rcx, [rcx+108h]
0x180016090  cmp     [rcx+98h], r9b
0x180016097  jnz     short locret_1800160FB
0x180016099  mov     byte ptr [rcx+98h], 3
0x1800160a0  mov     [rcx+9Ah], r9w
0x1800160a8  mov     [rcx+0A0h], r8
0x1800160af  retn
0x1800160b0  mov     rax, [rcx+108h]
0x1800160b7  test    dword ptr [rax+38h], 200h
0x1800160be  jnz     short loc_1800160DB
0x1800160c0  cmp     [rax+98h], r9b
0x1800160c7  jnz     short locret_1800160FB
0x1800160c9  mov     byte ptr [rax+98h], 3
0x1800160d0  mov     word ptr [rax+9Ah], 4001h
0x1800160d9  jmp     short loc_1800160F4
0x1800160db  cmp     [rax+98h], r9b
0x1800160e2  jnz     short locret_1800160FB
0x1800160e4  mov     byte ptr [rax+98h], 1
0x1800160eb  mov     word ptr [rax+9Ah], 8000h
0x1800160f4  mov     [rax+0A0h], r9
0x1800160fb  retn
```
