# UmpoUpdateSmartSuspendThresholds

- ea: `0x180017d54`
- end: `0x180017e05`
- name: `UmpoUpdateSmartSuspendThresholds`
- size: `177`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180017868`

## callees

- `0x180017614`
- `0x180017d54`
- `0x180017e0c`

## pseudocode

```c
__int64 UmpoUpdateSmartSuspendThresholds()
{
  __int64 result; // rax
  __int64 v1; // rcx
  unsigned __int64 v2; // rax
  __int64 v3; // r8
  __int64 v4; // r10
  unsigned int v5; // r9d
  unsigned int v6; // eax
  unsigned int v7; // r11d
  __int64 v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rdx

  result = Feature_SmartSuspend_Thresholds__private_IsEnabledDeviceUsageNoInline();
  if ( (_DWORD)result )
  {
    v2 = Feature_SmartSuspend_Thresholds__private_featureState;
    if ( (Feature_SmartSuspend_Thresholds__private_featureState & 8) == 0 )
      v2 = wil_details_FeatureStateCache_ReevaluateCachedVariantState(
             v1,
             Feature_SmartSuspend_Thresholds__private_featureState);
    result = HIDWORD(v2);
    v3 = 0;
    do
    {
      v4 = 0;
      do
      {
        v5 = 10 * (result & 0xF);
        if ( v5 >= 0x64 )
          LOBYTE(v5) = 100;
        v6 = (unsigned int)result >> 4;
        v7 = 10 * (v6 & 0xF);
        if ( v7 >= 0x64 )
          LOBYTE(v7) = 100;
        result = v6 >> 4;
        v8 = 0;
        do
        {
          v9 = v8 + 2 * v3;
          ++v8;
          v10 = (unsigned int)v3 + v9;
          *((_BYTE *)&UmpoSmartSuspendMetadata[v10] + 4 * v4) = v5;
          *((_BYTE *)&UmpoSmartSuspendMetadata[v10] + 4 * v4 + 1) = v7;
        }
        while ( v8 != 3 );
        v4 = (unsigned int)(v4 + 1);
      }
      while ( (int)v4 < 2 );
      v3 = (unsigned int)(v3 + 1);
    }
    while ( (int)v3 < 2 );
  }
  return result;
}

```

## disassembly

```asm
0x180017d54  push    rbx
0x180017d56  push    rsi
0x180017d57  push    rdi
0x180017d58  push    r14
0x180017d5a  push    r15
0x180017d5c  sub     rsp, 20h
0x180017d60  call    Feature_SmartSuspend_Thresholds__private_IsEnabledDeviceUsageNoInline
0x180017d65  test    eax, eax
0x180017d67  jz      loc_180017DF9
0x180017d6d  mov     rax, cs:Feature_SmartSuspend_Thresholds__private_featureState
0x180017d74  test    al, 8
0x180017d76  jnz     short loc_180017D80
0x180017d78  mov     rdx, rax
0x180017d7b  call    wil_details_FeatureStateCache_ReevaluateCachedVariantState
0x180017d80  shr     rax, 20h
0x180017d84  lea     r15, UmpoSmartSuspendMetadata
0x180017d8b  xor     r8d, r8d
0x180017d8e  xor     r10d, r10d
0x180017d91  mov     edi, r8d
0x180017d94  mov     ecx, eax
0x180017d96  and     ecx, 0Fh
0x180017d99  lea     r9d, [rcx+rcx*4]
0x180017d9d  add     r9d, r9d
0x180017da0  cmp     r9d, 64h ; 'd'
0x180017da4  jb      short loc_180017DA9
0x180017da6  mov     r9b, 64h ; 'd'
0x180017da9  shr     eax, 4
0x180017dac  mov     ecx, eax
0x180017dae  and     ecx, 0Fh
0x180017db1  lea     r11d, [rcx+rcx*4]
0x180017db5  add     r11d, r11d
0x180017db8  cmp     r11d, 64h ; 'd'
0x180017dbc  jb      short loc_180017DC1
0x180017dbe  mov     r11b, 64h ; 'd'
0x180017dc1  shr     eax, 4
0x180017dc4  lea     rsi, [r15+r10*4]
0x180017dc8  xor     ebx, ebx
0x180017dca  lea     r14, [r15+r10*4]
0x180017dce  lea     rdx, [rbx+r8*2]
0x180017dd2  inc     rbx
0x180017dd5  add     rdx, rdi
0x180017dd8  mov     [rsi+rdx*8], r9b
0x180017ddc  mov     [r14+rdx*8+1], r11b
0x180017de1  cmp     rbx, 3
0x180017de5  jnz     short loc_180017DCE
0x180017de7  inc     r10d
0x180017dea  cmp     r10d, 2
0x180017dee  jl      short loc_180017D94
0x180017df0  inc     r8d
0x180017df3  cmp     r8d, 2
0x180017df7  jl      short loc_180017D8E
0x180017df9  add     rsp, 20h
0x180017dfd  pop     r15
0x180017dff  pop     r14
0x180017e01  pop     rdi
0x180017e02  pop     rsi
0x180017e03  pop     rbx
0x180017e04  retn
```
