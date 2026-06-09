# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x140023200`
- end: `0x140023324`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140017a10`
- `0x140023200`
- `0x14002332c`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14002327f`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14002327f`

## pseudocode

```c
__int64 wil_details_ReevaluateOnFeatureConfigurationChange()
{
  __int64 *i; // rbx
  __int64 v1; // rcx
  int v2; // eax
  __int16 v3; // dx
  __int16 v4; // dx
  __int64 v6; // [rsp+20h] [rbp-28h] BYREF
  __int64 v7; // [rsp+28h] [rbp-20h] BYREF
  int v8; // [rsp+30h] [rbp-18h]

  for ( i = wil_details_featureDescriptors_a; i < wil_details_featureDescriptors_a; ++i )
  {
    if ( *i )
    {
LABEL_23:
      if ( !i )
        return wil_details_EvaluateFeatureDependencies();
      if ( !*((_BYTE *)i + 29) && !*((_BYTE *)i + 30) && !*((_BYTE *)i + 28) )
      {
        v1 = *((unsigned int *)i + 6);
        v7 = 0;
        v8 = 0;
        v6 = 0;
        v2 = ((__int64 (__fastcall *)(__int64, __int64, __int64 *, __int64 *))RtlQueryFeatureConfiguration)(
               v1,
               1,
               &v6,
               &v7);
        if ( v2 == -2147483614 || v2 == -1073741275 )
          goto LABEL_16;
        if ( v2 )
        {
          if ( v2 == 279 )
          {
            v3 = BYTE4(v7) & 0x80;
            goto LABEL_15;
          }
LABEL_16:
          v4 = 518;
        }
        else
        {
          v3 = BYTE4(v7) & 0xB0 | (4 * (BYTE4(v7) & 0x40));
LABEL_15:
          v4 = (8 * v3) | 0x206;
        }
        _InterlockedXor((volatile signed __int32 *)*i, ((unsigned __int16)v4 ^ (unsigned __int16)*(_DWORD *)*i) & 0xF80);
      }
      for ( i += 7; i < wil_details_featureDescriptors_a; ++i )
      {
        if ( *i )
          goto LABEL_23;
      }
      return wil_details_EvaluateFeatureDependencies();
    }
  }
  return wil_details_EvaluateFeatureDependencies();
}

```

## disassembly

```asm
0x140023200  mov     [rsp+arg_0], rbx
0x140023205  push    rsi
0x140023206  sub     rsp, 40h
0x14002320a  mov     rax, cs:__security_cookie
0x140023211  xor     rax, rsp
0x140023214  mov     [rsp+48h+var_10], rax
0x140023219  lea     rbx, wil_details_featureDescriptors_a
0x140023220  lea     rsi, wil_details_featureDescriptors_a
0x140023227  jmp     short loc_140023237
0x140023229  cmp     qword ptr [rbx], 0
0x14002322d  jnz     loc_1400232FD
0x140023233  add     rbx, 8
0x140023237  cmp     rbx, rsi
0x14002323a  jb      short loc_140023229
0x14002323c  jmp     loc_140023306
0x140023241  cmp     byte ptr [rbx+1Dh], 0
0x140023245  jnz     loc_1400232E6
0x14002324b  cmp     byte ptr [rbx+1Eh], 0
0x14002324f  jnz     loc_1400232E6
0x140023255  cmp     byte ptr [rbx+1Ch], 0
0x140023259  jnz     loc_1400232E6
0x14002325f  mov     ecx, [rbx+18h]
0x140023262  lea     r9, [rsp+48h+var_20]
0x140023267  xor     eax, eax
0x140023269  lea     r8, [rsp+48h+var_28]
0x14002326e  mov     [rsp+48h+var_20], rax
0x140023273  mov     [rsp+48h+var_18], eax
0x140023277  mov     [rsp+48h+var_28], rax
0x14002327c  lea     edx, [rax+1]
0x14002327f  call    cs:__imp_RtlQueryFeatureConfiguration
0x140023286  nop     dword ptr [rax+rax+00h]
0x14002328b  cmp     eax, 80000022h
0x140023290  jz      short loc_1400232CE
0x140023292  cmp     eax, 0C0000225h
0x140023297  jz      short loc_1400232CE
0x140023299  test    eax, eax
0x14002329b  jz      short loc_1400232B0
0x14002329d  cmp     eax, 117h
0x1400232a2  jnz     short loc_1400232CE
0x1400232a4  mov     edx, dword ptr [rsp+48h+var_20+4]
0x1400232a8  and     edx, 80h
0x1400232ae  jmp     short loc_1400232C3
0x1400232b0  mov     eax, dword ptr [rsp+48h+var_20+4]
0x1400232b4  mov     edx, eax
0x1400232b6  and     edx, 40h
0x1400232b9  and     eax, 0B0h
0x1400232be  shl     edx, 2
0x1400232c1  or      edx, eax
0x1400232c3  shl     edx, 3
0x1400232c6  or      edx, 206h
0x1400232cc  jmp     short loc_1400232D3
0x1400232ce  mov     edx, 206h
0x1400232d3  mov     rax, [rbx]
0x1400232d6  mov     ecx, [rax]
0x1400232d8  mov     rax, [rbx]
0x1400232db  xor     ecx, edx
0x1400232dd  and     ecx, 0F80h
0x1400232e3  lock xor [rax], ecx
0x1400232e6  add     rbx, 38h ; '8'
0x1400232ea  jmp     short loc_1400232F6
0x1400232ec  cmp     qword ptr [rbx], 0
0x1400232f0  jnz     short loc_1400232FD
0x1400232f2  add     rbx, 8
0x1400232f6  cmp     rbx, rsi
0x1400232f9  jb      short loc_1400232EC
0x1400232fb  jmp     short loc_140023306
0x1400232fd  test    rbx, rbx
0x140023300  jnz     loc_140023241
0x140023306  call    wil_details_EvaluateFeatureDependencies
0x14002330b  mov     rcx, [rsp+48h+var_10]
0x140023310  xor     rcx, rsp; StackCookie
0x140023313  call    __security_check_cookie
0x140023318  mov     rbx, [rsp+48h+arg_0]
0x14002331d  add     rsp, 40h
0x140023321  pop     rsi
0x140023322  retn
```
