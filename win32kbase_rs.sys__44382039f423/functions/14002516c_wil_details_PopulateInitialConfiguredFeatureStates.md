# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x14002516c`
- end: `0x1400252eb`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140025008`

## callees

- `0x140017a10`
- `0x14002516c`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400251e8`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400251e8`

## pseudocode

```c
void wil_details_PopulateInitialConfiguredFeatureStates()
{
  __int64 *i; // rbx
  int v1; // eax
  _QWORD *v2; // rcx
  _QWORD *v3; // rcx
  __int64 v4; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+28h] [rbp-20h] BYREF
  int v6; // [rsp+30h] [rbp-18h]

  for ( i = wil_details_featureDescriptors_a; ; ++i )
  {
    if ( i >= wil_details_featureDescriptors_a )
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
    v2 = (_QWORD *)*i;
    i += 7;
    *v2 = v4;
    while ( i < wil_details_featureDescriptors_a )
    {
      if ( *i )
        goto LABEL_20;
      ++i;
    }
    return;
  }
  v4 = 518;
LABEL_23:
  v3 = (_QWORD *)*i;
  i += 7;
  *v3 = 518;
  while ( i < wil_details_featureDescriptors_a )
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
0x14002516c  mov     [rsp+arg_0], rbx
0x140025171  push    rsi
0x140025172  sub     rsp, 40h
0x140025176  mov     rax, cs:__security_cookie
0x14002517d  xor     rax, rsp
0x140025180  mov     [rsp+48h+var_10], rax
0x140025185  lea     rbx, wil_details_featureDescriptors_a
0x14002518c  lea     rsi, wil_details_featureDescriptors_a
0x140025193  jmp     short loc_1400251A3
0x140025195  cmp     qword ptr [rbx], 0
0x140025199  jnz     loc_14002528F
0x14002519f  add     rbx, 8
0x1400251a3  cmp     rbx, rsi
0x1400251a6  jb      short loc_140025195
0x1400251a8  jmp     loc_1400252D2
0x1400251ad  xor     eax, eax
0x1400251af  mov     [rsp+48h+var_20], rax
0x1400251b4  mov     [rsp+48h+var_18], eax
0x1400251b8  mov     [rsp+48h+var_28], rax
0x1400251bd  cmp     [rbx+1Dh], al
0x1400251c0  jnz     loc_14002525C
0x1400251c6  cmp     [rbx+1Eh], al
0x1400251c9  jnz     loc_14002525C
0x1400251cf  mov     al, [rbx+1Ch]
0x1400251d2  lea     r9, [rsp+48h+var_20]
0x1400251d7  mov     ecx, [rbx+18h]
0x1400251da  lea     r8, [rsp+48h+var_28]
0x1400251df  xor     edx, edx
0x1400251e1  sub     al, 2
0x1400251e3  cmp     al, 1
0x1400251e5  setnbe  dl
0x1400251e8  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400251ef  nop     dword ptr [rax+rax+00h]
0x1400251f4  cmp     eax, 80000022h
0x1400251f9  jz      loc_14002529A
0x1400251ff  cmp     eax, 0C0000225h
0x140025204  jz      short loc_14002525C
0x140025206  test    eax, eax
0x140025208  jz      short loc_140025231
0x14002520a  cmp     eax, 117h
0x14002520f  jnz     short loc_14002525C
0x140025211  mov     eax, dword ptr [rsp+48h+var_20+4]
0x140025215  and     eax, 80h
0x14002521a  mov     [rsp+48h+var_28], 0
0x140025223  shl     eax, 3
0x140025226  or      eax, 206h
0x14002522b  mov     dword ptr [rsp+48h+var_28], eax
0x14002522f  jmp     short loc_14002526D
0x140025231  mov     eax, dword ptr [rsp+48h+var_20+4]
0x140025235  mov     ecx, eax
0x140025237  and     ecx, 40h
0x14002523a  mov     [rsp+48h+var_28], 0
0x140025243  shl     ecx, 2
0x140025246  and     eax, 0B0h
0x14002524b  or      ecx, eax
0x14002524d  shl     ecx, 3
0x140025250  or      ecx, 206h
0x140025256  mov     dword ptr [rsp+48h+var_28], ecx
0x14002525a  jmp     short loc_14002526D
0x14002525c  mov     [rsp+48h+var_28], 0
0x140025265  mov     dword ptr [rsp+48h+var_28], 206h
0x14002526d  mov     rcx, [rbx]
0x140025270  add     rbx, 38h ; '8'
0x140025274  mov     rax, [rsp+48h+var_28]
0x140025279  mov     [rcx], rax
0x14002527c  jmp     short loc_140025288
0x14002527e  cmp     qword ptr [rbx], 0
0x140025282  jnz     short loc_14002528F
0x140025284  add     rbx, 8
0x140025288  cmp     rbx, rsi
0x14002528b  jb      short loc_14002527E
0x14002528d  jmp     short loc_1400252D2
0x14002528f  test    rbx, rbx
0x140025292  jnz     loc_1400251AD
0x140025298  jmp     short loc_1400252D2
0x14002529a  mov     [rsp+48h+var_28], 0
0x1400252a3  mov     dword ptr [rsp+48h+var_28], 206h
0x1400252ab  mov     rax, [rsp+48h+var_28]
0x1400252b0  mov     rcx, [rbx]
0x1400252b3  add     rbx, 38h ; '8'
0x1400252b7  mov     [rcx], rax
0x1400252ba  jmp     short loc_1400252C6
0x1400252bc  cmp     qword ptr [rbx], 0
0x1400252c0  jnz     short loc_1400252CD
0x1400252c2  add     rbx, 8
0x1400252c6  cmp     rbx, rsi
0x1400252c9  jb      short loc_1400252BC
0x1400252cb  jmp     short loc_1400252D2
0x1400252cd  test    rbx, rbx
0x1400252d0  jnz     short loc_1400252B0
0x1400252d2  mov     rcx, [rsp+48h+var_10]
0x1400252d7  xor     rcx, rsp; StackCookie
0x1400252da  call    __security_check_cookie
0x1400252df  mov     rbx, [rsp+48h+arg_0]
0x1400252e4  add     rsp, 40h
0x1400252e8  pop     rsi
0x1400252e9  retn
```
