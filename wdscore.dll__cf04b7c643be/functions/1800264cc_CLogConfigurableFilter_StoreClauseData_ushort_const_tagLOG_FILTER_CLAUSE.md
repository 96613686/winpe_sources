# CLogConfigurableFilter::StoreClauseData(ushort const *,tagLOG_FILTER_CLAUSE *)

- ea: `0x1800264cc`
- end: `0x180026549`
- name: `?StoreClauseData@CLogConfigurableFilter@@IEAAHPEBGPEAUtagLOG_FILTER_CLAUSE@@@Z`
- size: `125`
- prototype: `int(CLogConfigurableFilter *__hidden this, const unsigned __int16 *, struct tagLOG_FILTER_CLAUSE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180025630`

## callees

- `0x180021ea8`
- `0x180025bdc`
- `0x1800264cc`

## import_xrefs

- `msvcrt!_wtoi` at `0x180026516`
- `msvcrt!_wtoi` at `0x180026516`

## pseudocode

```c
_BOOL8 __fastcall CLogConfigurableFilter::StoreClauseData(
        CLogConfigurableFilter *this,
        const unsigned __int16 *a2,
        struct tagLOG_FILTER_CLAUSE *a3)
{
  int v3; // ecx
  CLogConfigurableFilter *v5; // rcx
  __int64 ParsedPatternW; // rax
  double v8; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)&v8 = this;
  v3 = *((_DWORD *)a3 + 2);
  if ( v3 )
  {
    v5 = (CLogConfigurableFilter *)(unsigned int)(v3 - 1);
    if ( (_DWORD)v5 )
    {
      if ( (_DWORD)v5 != 2 )
        return 0;
      v8 = 0.0;
      if ( !(unsigned int)CLogConfigurableFilter::ParseDateString(v5, a2, &v8) )
        return 0;
      *((double *)a3 + 2) = v8;
    }
    else
    {
      *((_DWORD *)a3 + 4) = _wtoi(a2);
    }
    return 1;
  }
  else
  {
    ParsedPatternW = CreateParsedPatternW(a2);
    *((_QWORD *)a3 + 2) = ParsedPatternW;
    return ParsedPatternW != 0;
  }
}

```

## disassembly

```asm
0x1800264cc  mov     [rsp+arg_0], rcx
0x1800264d1  push    rbx
0x1800264d2  sub     rsp, 20h
0x1800264d6  mov     ecx, [r8+8]
0x1800264da  mov     rbx, r8
0x1800264dd  test    ecx, ecx
0x1800264df  jz      short loc_18002652C
0x1800264e1  sub     ecx, 1; this
0x1800264e4  jz      short loc_180026513
0x1800264e6  cmp     ecx, 2
0x1800264e9  jnz     short loc_18002650F
0x1800264eb  xorps   xmm0, xmm0
0x1800264ee  lea     r8, [rsp+28h+arg_0]; double *
0x1800264f3  movsd   [rsp+28h+arg_0], xmm0
0x1800264f9  call    ?ParseDateString@CLogConfigurableFilter@@IEAAHPEBGPEAN@Z; CLogConfigurableFilter::ParseDateString(ushort const *,double *)
0x1800264fe  test    eax, eax
0x180026500  jz      short loc_18002650F
0x180026502  movsd   xmm0, [rsp+28h+arg_0]
0x180026508  movsd   qword ptr [rbx+10h], xmm0
0x18002650d  jmp     short loc_180026525
0x18002650f  xor     eax, eax
0x180026511  jmp     short loc_180026542
0x180026513  mov     rcx, rdx; String
0x180026516  call    cs:__imp__wtoi
0x18002651d  nop     dword ptr [rax+rax+00h]
0x180026522  mov     [rbx+10h], eax
0x180026525  mov     eax, 1
0x18002652a  jmp     short loc_180026542
0x18002652c  mov     rcx, rdx
0x18002652f  call    CreateParsedPatternW
0x180026534  xor     ecx, ecx
0x180026536  mov     [rbx+10h], rax
0x18002653a  test    rax, rax
0x18002653d  setnz   cl
0x180026540  mov     eax, ecx
0x180026542  add     rsp, 20h
0x180026546  pop     rbx
0x180026547  retn
```
