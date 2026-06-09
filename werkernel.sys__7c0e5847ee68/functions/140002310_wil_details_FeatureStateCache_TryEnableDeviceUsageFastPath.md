# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x140002310`
- end: `0x14000234c`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `60`
- prototype: `void __fastcall(unsigned __int8, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140002354`

## callees

- `0x140002310`

## pseudocode

```c
void __fastcall wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(unsigned __int8 a1, int a2)
{
  int v2; // edx
  int v3; // r8d
  signed __int32 v4; // eax
  signed __int32 v5; // ett

  v2 = a2 - 3;
  if ( v2 )
  {
    if ( v2 != 1 )
      return;
    v3 = 32;
  }
  else
  {
    v3 = 16;
  }
  v4 = *Feature_Servicing_WerReportBootLKD__private_descriptor[0];
  do
  {
    if ( (v4 & 2) == 0 )
      break;
    if ( ((a1 ^ (unsigned __int8)v4) & 1) != 0 )
      break;
    v5 = v4;
    v4 = _InterlockedCompareExchange(Feature_Servicing_WerReportBootLKD__private_descriptor[0], v4 | v3, v4);
  }
  while ( v5 != v4 );
}

```

## disassembly

```asm
0x140002310  sub     edx, 3
0x140002313  jz      short loc_140002320
0x140002315  cmp     edx, 1
0x140002318  jnz     short locret_14000234B
0x14000231a  lea     r8d, [rdx+1Fh]
0x14000231e  jmp     short loc_140002326
0x140002320  mov     r8d, 10h
0x140002326  mov     r9, cs:Feature_Servicing_WerReportBootLKD__private_descriptor
0x14000232d  mov     eax, [r9]
0x140002330  jmp     short loc_140002347
0x140002332  mov     edx, eax
0x140002334  xor     edx, ecx
0x140002336  test    dl, 1
0x140002339  jnz     short locret_14000234B
0x14000233b  mov     edx, r8d
0x14000233e  or      edx, eax
0x140002340  lock cmpxchg [r9], edx
0x140002345  jz      short locret_14000234B
0x140002347  test    al, 2
0x140002349  jnz     short loc_140002332
0x14000234b  retn
```
