# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x140094840`
- end: `0x1400949bf`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400946d8`

## callees

- `0x140045530`
- `0x140094840`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400948bc`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400948bc`

## pseudocode

```c
void wil_details_PopulateInitialConfiguredFeatureStates()
{
  _UNKNOWN **i; // rbx
  int v1; // eax
  __int64 *v2; // rcx
  _QWORD *v3; // rcx
  __int64 v4; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+28h] [rbp-20h] BYREF
  int v6; // [rsp+30h] [rbp-18h]

  for ( i = &wil_details_featureDescriptors_a; ; ++i )
  {
    if ( i >= (_UNKNOWN **)wil_details_featureDescriptors_z )
      return;
    if ( *i )
      break;
  }
LABEL_20:
  if ( !i )
    return;
  v5 = 0;
  v6 = 0;
  v4 = 0;
  if ( *((_BYTE *)i + 29) || *((_BYTE *)i + 30) )
    goto LABEL_14;
  v1 = ((__int64 (__fastcall *)(_QWORD, bool, __int64 *, __int64 *))RtlQueryFeatureConfiguration)(
         *((unsigned int *)i + 6),
         (unsigned __int8)(*((_BYTE *)i + 28) - 2) > 1u,
         &v4,
         &v5);
  if ( v1 != -2147483614 )
  {
    if ( v1 != -1073741275 )
    {
      if ( !v1 )
      {
        v4 = (8 * (BYTE4(v5) & 0xB0 | (4 * (BYTE4(v5) & 0x40u)))) | 0x206LL;
        goto LABEL_15;
      }
      if ( v1 == 279 )
      {
        v4 = (8 * (BYTE4(v5) & 0x80u)) | 0x206LL;
        goto LABEL_15;
      }
    }
LABEL_14:
    v4 = 518;
LABEL_15:
    v2 = (__int64 *)*i;
    i += 7;
    *v2 = v4;
    while ( i < (_UNKNOWN **)wil_details_featureDescriptors_z )
    {
      if ( *i )
        goto LABEL_20;
      ++i;
    }
    return;
  }
  v4 = 518;
LABEL_23:
  v3 = *i;
  i += 7;
  *v3 = 518;
  while ( i < (_UNKNOWN **)wil_details_featureDescriptors_z )
  {
    if ( *i )
    {
      if ( i )
        goto LABEL_23;
      return;
    }
    ++i;
  }
}

```

## disassembly

```asm
0x140094840  mov     [rsp+arg_0], rbx
0x140094845  push    rsi
0x140094846  sub     rsp, 40h
0x14009484a  mov     rax, cs:__security_cookie
0x140094851  xor     rax, rsp
0x140094854  mov     [rsp+48h+var_10], rax
0x140094859  lea     rbx, wil_details_featureDescriptors_a
0x140094860  lea     rsi, wil_details_featureDescriptors_z
0x140094867  jmp     short loc_140094877
0x140094869  cmp     qword ptr [rbx], 0
0x14009486d  jnz     loc_140094963
0x140094873  add     rbx, 8
0x140094877  cmp     rbx, rsi
0x14009487a  jb      short loc_140094869
0x14009487c  jmp     loc_1400949A6
0x140094881  xor     eax, eax
0x140094883  mov     [rsp+48h+var_20], rax
0x140094888  mov     [rsp+48h+var_18], eax
0x14009488c  mov     [rsp+48h+var_28], rax
0x140094891  cmp     [rbx+1Dh], al
0x140094894  jnz     loc_140094930
0x14009489a  cmp     [rbx+1Eh], al
0x14009489d  jnz     loc_140094930
0x1400948a3  mov     al, [rbx+1Ch]
0x1400948a6  lea     r9, [rsp+48h+var_20]
0x1400948ab  mov     ecx, [rbx+18h]
0x1400948ae  lea     r8, [rsp+48h+var_28]
0x1400948b3  xor     edx, edx
0x1400948b5  sub     al, 2
0x1400948b7  cmp     al, 1
0x1400948b9  setnbe  dl
0x1400948bc  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400948c3  nop     dword ptr [rax+rax+00h]
0x1400948c8  cmp     eax, 80000022h
0x1400948cd  jz      loc_14009496E
0x1400948d3  cmp     eax, 0C0000225h
0x1400948d8  jz      short loc_140094930
0x1400948da  test    eax, eax
0x1400948dc  jz      short loc_140094905
0x1400948de  cmp     eax, 117h
0x1400948e3  jnz     short loc_140094930
0x1400948e5  mov     eax, dword ptr [rsp+48h+var_20+4]
0x1400948e9  and     eax, 80h
0x1400948ee  mov     [rsp+48h+var_28], 0
0x1400948f7  shl     eax, 3
0x1400948fa  or      eax, 206h
0x1400948ff  mov     dword ptr [rsp+48h+var_28], eax
0x140094903  jmp     short loc_140094941
0x140094905  mov     eax, dword ptr [rsp+48h+var_20+4]
0x140094909  mov     ecx, eax
0x14009490b  and     ecx, 40h
0x14009490e  mov     [rsp+48h+var_28], 0
0x140094917  shl     ecx, 2
0x14009491a  and     eax, 0B0h
0x14009491f  or      ecx, eax
0x140094921  shl     ecx, 3
0x140094924  or      ecx, 206h
0x14009492a  mov     dword ptr [rsp+48h+var_28], ecx
0x14009492e  jmp     short loc_140094941
0x140094930  mov     [rsp+48h+var_28], 0
0x140094939  mov     dword ptr [rsp+48h+var_28], 206h
0x140094941  mov     rcx, [rbx]
0x140094944  add     rbx, 38h ; '8'
0x140094948  mov     rax, [rsp+48h+var_28]
0x14009494d  mov     [rcx], rax
0x140094950  jmp     short loc_14009495C
0x140094952  cmp     qword ptr [rbx], 0
0x140094956  jnz     short loc_140094963
0x140094958  add     rbx, 8
0x14009495c  cmp     rbx, rsi
0x14009495f  jb      short loc_140094952
0x140094961  jmp     short loc_1400949A6
0x140094963  test    rbx, rbx
0x140094966  jnz     loc_140094881
0x14009496c  jmp     short loc_1400949A6
0x14009496e  mov     [rsp+48h+var_28], 0
0x140094977  mov     dword ptr [rsp+48h+var_28], 206h
0x14009497f  mov     rax, [rsp+48h+var_28]
0x140094984  mov     rcx, [rbx]
0x140094987  add     rbx, 38h ; '8'
0x14009498b  mov     [rcx], rax
0x14009498e  jmp     short loc_14009499A
0x140094990  cmp     qword ptr [rbx], 0
0x140094994  jnz     short loc_1400949A1
0x140094996  add     rbx, 8
0x14009499a  cmp     rbx, rsi
0x14009499d  jb      short loc_140094990
0x14009499f  jmp     short loc_1400949A6
0x1400949a1  test    rbx, rbx
0x1400949a4  jnz     short loc_140094984
0x1400949a6  mov     rcx, [rsp+48h+var_10]
0x1400949ab  xor     rcx, rsp; StackCookie
0x1400949ae  call    __security_check_cookie
0x1400949b3  mov     rbx, [rsp+48h+arg_0]
0x1400949b8  add     rsp, 40h
0x1400949bc  pop     rsi
0x1400949bd  retn
```
