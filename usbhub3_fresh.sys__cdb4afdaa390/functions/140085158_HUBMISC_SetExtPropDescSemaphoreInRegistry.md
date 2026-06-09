# HUBMISC_SetExtPropDescSemaphoreInRegistry

- ea: `0x140085158`
- end: `0x1400852a0`
- name: `HUBMISC_SetExtPropDescSemaphoreInRegistry`
- size: `328`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140023f90`

## callees

- `0x1400024b8`
- `0x140085158`
- `0x14008b354`

## pseudocode

```c
__int64 __fastcall HUBMISC_SetExtPropDescSemaphoreInRegistry(__int64 a1)
{
  int v2; // edx
  int v3; // ebx
  int v4; // r9d
  int v5; // ecx
  int v7; // [rsp+28h] [rbp-10h]
  int v8; // [rsp+48h] [rbp+10h] BYREF

  v8 = 1;
  v3 = HUBREG_WriteValueToDeviceHardwareKey(a1, (__int64)L"(*", 4u, 4, (__int64)&v8);
  if ( v3 >= 0 )
  {
    v8 = *(unsigned __int16 *)(a1 + 2008);
    v3 = HUBREG_WriteValueToDeviceHardwareKey(a1, (__int64)&g_RevisionId, 4u, 4, (__int64)&v8);
    if ( v3 >= 0 )
    {
      if ( (*(_DWORD *)(a1 + 2472) & 0x400) != 0 )
        v5 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 2536) + 4LL);
      else
        v5 = 0;
      v8 = v5;
      v3 = HUBREG_WriteValueToDeviceHardwareKey(a1, (__int64)&g_VendorRevision, 4u, 4, (__int64)&v8);
      if ( v3 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v4 = 63;
        goto LABEL_13;
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v4 = 62;
      goto LABEL_13;
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v4 = 61;
LABEL_13:
    v7 = v3;
    LOBYTE(v2) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
      v2,
      5,
      v4,
      (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids,
      v7);
  }
  return ((v3 >> 31) & 0xFFFFFFF4) + 4077;
}

```

## disassembly

```asm
0x140085158  mov     rax, rsp
0x14008515b  mov     [rax+8], rbx
0x14008515f  mov     [rax+18h], rsi
0x140085163  push    rdi
0x140085164  sub     rsp, 30h
0x140085168  mov     dword ptr [rax+10h], 1
0x14008516f  lea     rax, [rax+10h]
0x140085173  mov     esi, 4
0x140085178  mov     [rsp+38h+var_18], rax
0x14008517d  mov     r9d, esi
0x140085180  lea     rdx, g_ExtPropDescSemaphore; "(*"
0x140085187  mov     r8d, esi
0x14008518a  mov     rdi, rcx
0x14008518d  call    HUBREG_WriteValueToDeviceHardwareKey
0x140085192  mov     ebx, eax
0x140085194  test    eax, eax
0x140085196  jns     short loc_1400851B5
0x140085198  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008519f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400851a6  jz      loc_140085283
0x1400851ac  lea     r9d, [rsi+39h]
0x1400851b0  jmp     loc_14008525B
0x1400851b5  movzx   eax, word ptr [rdi+7D8h]
0x1400851bc  lea     rdx, g_RevisionId
0x1400851c3  mov     [rsp+38h+arg_8], eax
0x1400851c7  mov     r9d, esi
0x1400851ca  lea     rax, [rsp+38h+arg_8]
0x1400851cf  mov     r8d, esi
0x1400851d2  mov     rcx, rdi
0x1400851d5  mov     [rsp+38h+var_18], rax
0x1400851da  call    HUBREG_WriteValueToDeviceHardwareKey
0x1400851df  mov     ebx, eax
0x1400851e1  test    eax, eax
0x1400851e3  jns     short loc_140085201
0x1400851e5  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400851ec  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400851f3  jz      loc_140085283
0x1400851f9  mov     r9d, 3Eh ; '>'
0x1400851ff  jmp     short loc_14008525B
0x140085201  test    dword ptr [rdi+9A8h], 400h
0x14008520b  jz      short loc_14008521A
0x14008520d  mov     rax, [rdi+9E8h]
0x140085214  movzx   ecx, word ptr [rax+4]
0x140085218  jmp     short loc_14008521C
0x14008521a  xor     ecx, ecx
0x14008521c  mov     [rsp+38h+arg_8], ecx
0x140085220  lea     rax, [rsp+38h+arg_8]
0x140085225  mov     rcx, rdi
0x140085228  mov     [rsp+38h+var_18], rax
0x14008522d  mov     r9d, esi
0x140085230  lea     rdx, g_VendorRevision
0x140085237  mov     r8d, esi
0x14008523a  call    HUBREG_WriteValueToDeviceHardwareKey
0x14008523f  mov     ebx, eax
0x140085241  test    eax, eax
0x140085243  jns     short loc_140085283
0x140085245  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008524c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140085253  jz      short loc_140085283
0x140085255  mov     r9d, 3Fh ; '?'
0x14008525b  mov     rcx, [rdi+8]
0x14008525f  lea     rax, WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids
0x140085266  mov     [rsp+38h+var_10], ebx
0x14008526a  mov     r8d, 5
0x140085270  mov     dl, 2
0x140085272  mov     [rsp+38h+var_18], rax
0x140085277  mov     rcx, [rcx+598h]
0x14008527e  call    WPP_RECORDER_SF_d
0x140085283  mov     rsi, [rsp+38h+arg_10]
0x140085288  sar     ebx, 1Fh
0x14008528b  and     ebx, 0FFFFFFF4h
0x14008528e  lea     eax, [rbx+0FEDh]
0x140085294  mov     rbx, [rsp+38h+arg_0]
0x140085299  add     rsp, 30h
0x14008529d  pop     rdi
0x14008529e  retn
```
