# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x140010a80`
- end: `0x140010ba4`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `292`
- prototype: `void()`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140002750`
- `0x140010790`
- `0x140010a80`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140010aff`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140010aff`

## pseudocode

```c
void wil_details_ReevaluateOnFeatureConfigurationChange()
{
  __int64 **i; // rbx
  __int64 v1; // rcx
  int v2; // eax
  __int16 v3; // dx
  __int16 v4; // dx
  __int64 v5; // [rsp+20h] [rbp-28h] BYREF
  __int64 v6; // [rsp+28h] [rbp-20h] BYREF
  int v7; // [rsp+30h] [rbp-18h]

  for ( i = wil_details_featureDescriptors_a; i < (__int64 **)wil_details_featureDescriptors_z; ++i )
  {
    if ( *i )
    {
LABEL_23:
      if ( !i )
        break;
      if ( !*((_BYTE *)i + 29) && !*((_BYTE *)i + 30) && !*((_BYTE *)i + 28) )
      {
        v1 = *((unsigned int *)i + 6);
        v6 = 0;
        v7 = 0;
        v5 = 0;
        v2 = ((__int64 (__fastcall *)(__int64, __int64, __int64 *, __int64 *))RtlQueryFeatureConfiguration)(
               v1,
               1,
               &v5,
               &v6);
        if ( v2 == -2147483614 || v2 == -1073741275 )
          goto LABEL_16;
        if ( v2 )
        {
          if ( v2 == 279 )
          {
            v3 = BYTE4(v6) & 0x80;
            goto LABEL_15;
          }
LABEL_16:
          v4 = 518;
        }
        else
        {
          v3 = BYTE4(v6) & 0xB0 | (4 * (WORD2(v6) & 0xFFD0));
LABEL_15:
          v4 = (8 * v3) | 0x206;
        }
        _InterlockedXor((volatile signed __int32 *)*i, ((unsigned __int16)v4 ^ (unsigned __int16)*(_DWORD *)*i) & 0xF80);
      }
      for ( i += 7; i < (__int64 **)wil_details_featureDescriptors_z; ++i )
      {
        if ( *i )
          goto LABEL_23;
      }
      break;
    }
  }
  wil_details_EvaluateFeatureDependencies();
}

```

## disassembly

```asm
0x140010a80  mov     [rsp+arg_0], rbx
0x140010a85  push    rsi
0x140010a86  sub     rsp, 40h
0x140010a8a  mov     rax, cs:__security_cookie
0x140010a91  xor     rax, rsp
0x140010a94  mov     [rsp+48h+var_10], rax
0x140010a99  lea     rbx, wil_details_featureDescriptors_a
0x140010aa0  lea     rsi, wil_details_featureDescriptors_z
0x140010aa7  jmp     short loc_140010AB7
0x140010aa9  cmp     qword ptr [rbx], 0
0x140010aad  jnz     loc_140010B7D
0x140010ab3  add     rbx, 8
0x140010ab7  cmp     rbx, rsi
0x140010aba  jb      short loc_140010AA9
0x140010abc  jmp     loc_140010B86
0x140010ac1  cmp     byte ptr [rbx+1Dh], 0
0x140010ac5  jnz     loc_140010B66
0x140010acb  cmp     byte ptr [rbx+1Eh], 0
0x140010acf  jnz     loc_140010B66
0x140010ad5  cmp     byte ptr [rbx+1Ch], 0
0x140010ad9  jnz     loc_140010B66
0x140010adf  mov     ecx, [rbx+18h]
0x140010ae2  lea     r9, [rsp+48h+var_20]
0x140010ae7  xor     eax, eax
0x140010ae9  lea     r8, [rsp+48h+var_28]
0x140010aee  mov     [rsp+48h+var_20], rax
0x140010af3  mov     [rsp+48h+var_18], eax
0x140010af7  mov     [rsp+48h+var_28], rax
0x140010afc  lea     edx, [rax+1]
0x140010aff  call    cs:__imp_RtlQueryFeatureConfiguration
0x140010b06  nop     dword ptr [rax+rax+00h]
0x140010b0b  cmp     eax, 80000022h
0x140010b10  jz      short loc_140010B4E
0x140010b12  cmp     eax, 0C0000225h
0x140010b17  jz      short loc_140010B4E
0x140010b19  test    eax, eax
0x140010b1b  jz      short loc_140010B30
0x140010b1d  cmp     eax, 117h
0x140010b22  jnz     short loc_140010B4E
0x140010b24  mov     edx, dword ptr [rsp+48h+var_20+4]
0x140010b28  and     edx, 80h
0x140010b2e  jmp     short loc_140010B43
0x140010b30  mov     eax, dword ptr [rsp+48h+var_20+4]
0x140010b34  mov     edx, eax
0x140010b36  and     edx, 0FFFFFFD0h
0x140010b39  and     eax, 0B0h
0x140010b3e  shl     edx, 2
0x140010b41  or      edx, eax
0x140010b43  shl     edx, 3
0x140010b46  or      edx, 206h
0x140010b4c  jmp     short loc_140010B53
0x140010b4e  mov     edx, 206h
0x140010b53  mov     rax, [rbx]
0x140010b56  mov     ecx, [rax]
0x140010b58  mov     rax, [rbx]
0x140010b5b  xor     ecx, edx
0x140010b5d  and     ecx, 0F80h
0x140010b63  lock xor [rax], ecx
0x140010b66  add     rbx, 38h ; '8'
0x140010b6a  jmp     short loc_140010B76
0x140010b6c  cmp     qword ptr [rbx], 0
0x140010b70  jnz     short loc_140010B7D
0x140010b72  add     rbx, 8
0x140010b76  cmp     rbx, rsi
0x140010b79  jb      short loc_140010B6C
0x140010b7b  jmp     short loc_140010B86
0x140010b7d  test    rbx, rbx
0x140010b80  jnz     loc_140010AC1
0x140010b86  call    wil_details_EvaluateFeatureDependencies
0x140010b8b  mov     rcx, [rsp+48h+var_10]
0x140010b90  xor     rcx, rsp; StackCookie
0x140010b93  call    __security_check_cookie
0x140010b98  mov     rbx, [rsp+48h+arg_0]
0x140010b9d  add     rsp, 40h
0x140010ba1  pop     rsi
0x140010ba2  retn
```
