# WinSetupMonMessageAddOrUpdateTrackedPathOverride

- ea: `0x14001e2ec`
- end: `0x14001e45d`
- name: `WinSetupMonMessageAddOrUpdateTrackedPathOverride`
- size: `369`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140007668`

## callees

- `0x140001220`
- `0x140005de4`
- `0x14000f930`
- `0x14000fd40`
- `0x14001e044`
- `0x14001e10c`
- `0x14001e2ec`

## pseudocode

```c
__int64 __fastcall WinSetupMonMessageAddOrUpdateTrackedPathOverride(char a1, void *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  int updated; // ebx
  __int64 v7; // r8
  __int64 v8; // r8
  const UNICODE_STRING *v9; // r8
  const UNICODE_STRING *v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int128 v14; // [rsp+38h] [rbp-A0h] BYREF
  __int128 v15; // [rsp+48h] [rbp-90h] BYREF
  UNICODE_STRING v16; // [rsp+58h] [rbp-80h] BYREF
  unsigned int v17[26]; // [rsp+70h] [rbp-68h] BYREF

  memset(v17, 0, 0x40u);
  v16 = 0;
  v15 = 0;
  v14 = 0;
  if ( a1 )
    RtlCopyFromUser(v17, a2, 0x40u);
  else
    RtlCopyVolatileMemory(v17, a2, 0x40u);
  if ( LOWORD(v17[2]) && (LOWORD(v17[6]) || LOWORD(v17[10])) && (LOWORD(v17[10]) || !LOBYTE(v17[14])) )
  {
    LOBYTE(v5) = a1;
    updated = WinSetupMonDuplicateCapturedUnicodeStringFromMode(&v16, &v17[2], v5);
    if ( updated >= 0 )
    {
      LOBYTE(v7) = a1;
      updated = WinSetupMonDuplicateCapturedUnicodeStringFromMode(&v15, &v17[6], v7);
      if ( updated >= 0 )
      {
        LOBYTE(v8) = a1;
        updated = WinSetupMonDuplicateCapturedUnicodeStringFromMode(&v14, &v17[10], v8);
        if ( updated >= 0 )
        {
          v9 = (const UNICODE_STRING *)&v14;
          if ( !(_WORD)v14 )
            v9 = 0;
          v10 = (const UNICODE_STRING *)&v15;
          if ( !(_WORD)v15 )
            v10 = 0;
          updated = AddOrUpdateTrackedPathOverride(&v16, v10, v9, v17[14], v17[15]);
        }
      }
    }
  }
  else
  {
    updated = -1073741811;
  }
  LOBYTE(v4) = a1;
  WinSetupMonFreeCapturedUnicodeStringFromMode(&v14, v4);
  LOBYTE(v11) = a1;
  WinSetupMonFreeCapturedUnicodeStringFromMode(&v15, v11);
  LOBYTE(v12) = a1;
  WinSetupMonFreeCapturedUnicodeStringFromMode(&v16, v12);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x14001e2ec  mov     [rsp+arg_0], cl
0x14001e2f0  push    rbx
0x14001e2f1  push    rsi
0x14001e2f2  push    rdi
0x14001e2f3  push    r14
0x14001e2f5  sub     rsp, 0B8h
0x14001e2fc  mov     rbx, rdx
0x14001e2ff  mov     dil, cl
0x14001e302  mov     r14d, 40h ; '@'
0x14001e308  mov     r8d, r14d; Size
0x14001e30b  xor     edx, edx; Val
0x14001e30d  lea     rcx, [rsp+0D8h+var_68]; void *
0x14001e312  call    memset
0x14001e317  xorps   xmm0, xmm0
0x14001e31a  movups  xmmword ptr [rsp+0D8h+var_80.Length], xmm0
0x14001e31f  xorps   xmm1, xmm1
0x14001e322  movups  [rsp+0D8h+var_90], xmm1
0x14001e327  movups  [rsp+0D8h+var_A0], xmm0
0x14001e32c  xor     esi, esi
0x14001e32e  mov     r8d, r14d; Size
0x14001e331  mov     rdx, rbx; Src
0x14001e334  lea     rcx, [rsp+0D8h+var_68]; void *
0x14001e339  test    dil, dil
0x14001e33c  jz      short loc_14001E345
0x14001e33e  call    RtlCopyFromUser
0x14001e343  jmp     short loc_14001E34B
0x14001e345  call    RtlCopyVolatileMemory
0x14001e34a  nop
0x14001e34b  cmp     [rsp+0D8h+var_60], si
0x14001e350  jz      loc_14001E415
0x14001e356  cmp     [rsp+0D8h+var_50], si
0x14001e35e  jnz     short loc_14001E36E
0x14001e360  cmp     [rsp+0D8h+var_40], si
0x14001e368  jz      loc_14001E415
0x14001e36e  cmp     [rsp+0D8h+var_40], si
0x14001e376  jnz     short loc_14001E386
0x14001e378  cmp     [rsp+0D8h+var_30], sil
0x14001e380  jnz     loc_14001E415
0x14001e386  mov     r8b, dil
0x14001e389  lea     rdx, [rsp+0D8h+var_60]
0x14001e38e  lea     rcx, [rsp+0D8h+var_80]
0x14001e393  call    WinSetupMonDuplicateCapturedUnicodeStringFromMode
0x14001e398  mov     ebx, eax
0x14001e39a  test    eax, eax
0x14001e39c  js      loc_14001E426
0x14001e3a2  mov     r8b, dil
0x14001e3a5  lea     rdx, [rsp+0D8h+var_50]
0x14001e3ad  lea     rcx, [rsp+0D8h+var_90]
0x14001e3b2  call    WinSetupMonDuplicateCapturedUnicodeStringFromMode
0x14001e3b7  mov     ebx, eax
0x14001e3b9  test    eax, eax
0x14001e3bb  js      short loc_14001E426
0x14001e3bd  mov     r8b, dil
0x14001e3c0  lea     rdx, [rsp+0D8h+var_40]
0x14001e3c8  lea     rcx, [rsp+0D8h+var_A0]
0x14001e3cd  call    WinSetupMonDuplicateCapturedUnicodeStringFromMode
0x14001e3d2  mov     ebx, eax
0x14001e3d4  test    eax, eax
0x14001e3d6  js      short loc_14001E426
0x14001e3d8  lea     r8, [rsp+0D8h+var_A0]
0x14001e3dd  cmp     word ptr [rsp+0D8h+var_A0], si
0x14001e3e2  cmovbe  r8, rsi
0x14001e3e6  lea     rdx, [rsp+0D8h+var_90]
0x14001e3eb  cmp     word ptr [rsp+0D8h+var_90], si
0x14001e3f0  cmovbe  rdx, rsi
0x14001e3f4  mov     eax, [rsp+0D8h+var_2C]
0x14001e3fb  mov     [rsp+0D8h+var_B8], eax
0x14001e3ff  mov     r9b, [rsp+0D8h+var_30]
0x14001e407  lea     rcx, [rsp+0D8h+var_80]
0x14001e40c  call    ?AddOrUpdateTrackedPathOverride@@YAJPEBU_UNICODE_STRING@@00EW4_TRACKING_MODE@@@Z; AddOrUpdateTrackedPathOverride(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar,_TRACKING_MODE)
0x14001e411  mov     ebx, eax
0x14001e413  jmp     short loc_14001E426
0x14001e415  mov     ebx, 0C000000Dh
0x14001e41a  jmp     short loc_14001E426
0x14001e41c  mov     ebx, eax
0x14001e41e  mov     dil, [rsp+0D8h+arg_0]
0x14001e426  mov     dl, dil
0x14001e429  lea     rcx, [rsp+0D8h+var_A0]
0x14001e42e  call    WinSetupMonFreeCapturedUnicodeStringFromMode
0x14001e433  mov     dl, dil
0x14001e436  lea     rcx, [rsp+0D8h+var_90]
0x14001e43b  call    WinSetupMonFreeCapturedUnicodeStringFromMode
0x14001e440  mov     dl, dil
0x14001e443  lea     rcx, [rsp+0D8h+var_80]
0x14001e448  call    WinSetupMonFreeCapturedUnicodeStringFromMode
0x14001e44d  mov     eax, ebx
0x14001e44f  add     rsp, 0B8h
0x14001e456  pop     r14
0x14001e458  pop     rdi
0x14001e459  pop     rsi
0x14001e45a  pop     rbx
0x14001e45b  retn
0x140021c38  push    rbp
0x140021c3a  sub     rsp, 30h
0x140021c3e  mov     rbp, rdx
0x140021c41  xor     eax, eax
0x140021c43  cmp     [rbp+0E0h], al
0x140021c49  setnz   al
0x140021c4c  mov     [rbp+30h], eax
0x140021c4f  mov     eax, [rbp+30h]
0x140021c52  add     rsp, 30h
0x140021c56  pop     rbp
0x140021c57  retn
```
