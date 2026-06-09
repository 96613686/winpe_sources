# CcWriteBehindInternal

- ea: `0x1402a1b30`
- end: `0x1402a1d65`
- name: `CcWriteBehindInternal`
- size: `565`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1402a1880`

## callees

- `0x1402a06fc`
- `0x1402a0d60`
- `0x1402a1138`
- `0x1402a1280`
- `0x1402a1b30`
- `0x1402a1d6c`
- `0x1402a21fc`
- `0x1402a2f90`
- `0x1403631f0`
- `0x140367c90`
- `0x1406f7380`

## string_xrefs

- `0x1402a1d03`: `[%04x:%04x]CcWriteBehindInternal: WBPreProcess FAILED(%lx): PVCM:%p(vid:%2lx)\n`
- `0x140709c23`: `[%04x:%04x]CcWriteBehindInternal: PostProc:%d, Retry:%d, PVCM:%p(vid:%2lx)\n`
- `0x1402a1c94`: `[%04x:%04x]CcFlushCachePriv: PreProcess returned FALSE, nothing to do (SOP=%p, IoStatus=0x%x)\n`

## pseudocode

```c
ULONG __fastcall CcWriteBehindInternal(__int64 a1)
{
  __int128 *v1; // r14
  __int128 *v3; // rdi
  const void *v4; // rsi
  ULONG result; // eax
  char v6; // cl
  char v7; // di
  _DWORD *v8; // rcx
  int v9; // edx
  _DWORD *v10; // r8
  int v11; // r10d
  __int128 v12; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v13[16]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v14; // [rsp+70h] [rbp-90h]
  const void *v15; // [rsp+78h] [rbp-88h]
  __int64 v16; // [rsp+A8h] [rbp-58h]
  __int64 v17; // [rsp+B0h] [rbp-50h] BYREF
  __int64 *v18; // [rsp+B8h] [rbp-48h]
  __int64 *v19; // [rsp+C0h] [rbp-40h]
  int v20; // [rsp+C8h] [rbp-38h]
  char v21; // [rsp+CCh] [rbp-34h]
  __int128 *v22; // [rsp+D0h] [rbp-30h]
  char v23; // [rsp+E4h] [rbp-1Ch]
  __int16 v24; // [rsp+E8h] [rbp-18h]
  char v25; // [rsp+EBh] [rbp-15h]
  __int64 v26; // [rsp+148h] [rbp+48h]
  LARGE_INTEGER PerformanceCounter; // [rsp+150h] [rbp+50h]
  int v28; // [rsp+158h] [rbp+58h]
  __int64 v29; // [rsp+168h] [rbp+68h]

  v1 = *(__int128 **)(a1 + 24);
  while ( 1 )
  {
    memset_0(v13, 0, 0x110u);
    v22 = v1;
    v24 = 0;
    v29 = a1;
    v25 = 1;
    if ( (unsigned int)CcWriteBehindPreProcess(v13) == 1 )
      break;
    v3 = &v12;
    v4 = v15;
    v19 = &CcNoDelay;
    v20 = 1;
    if ( v1 )
      v3 = v1;
    v21 = 0;
    v22 = v3;
    v16 = 0;
    v12 = 0;
    if ( v18 )
    {
      v17 = *v18;
      v18 = &v17;
    }
    if ( (unsigned __int8)CcFlushCachePreProcess(v13) )
    {
      if ( v23 )
        v19 = 0;
      if ( v14 && (*(_DWORD *)(v14 + 152) & 0x4000000) == 0 )
      {
        do
        {
          if ( !(unsigned __int8)CcFlushCacheAcquireRange(v13) )
            break;
          CcFlushCacheOneRange(v13);
        }
        while ( (unsigned __int8)CcFlushCachePostProcessOneRange(v13) );
        if ( v26 && v28 )
          PerformanceCounter = KeQueryPerformanceCounter(0);
      }
      CcFlushCachePostProcess(v13);
    }
    else
    {
      DbgPrintEx(
        0x7Fu,
        3u,
        "[%04x:%04x]CcFlushCachePriv: PreProcess returned FALSE, nothing to do (SOP=%p, IoStatus=0x%x)\n",
        LODWORD(KeGetCurrentThread()[1].CycleTime),
        KeGetCurrentThread()[1].CurrentRunTime,
        v4,
        *(_DWORD *)v3);
    }
    result = CcWriteBehindPostProcess(v13, 0);
    v6 = HIBYTE(v24);
    v7 = result;
    if ( !(_BYTE)result || HIBYTE(v24) )
    {
      v10 = *(_DWORD **)(a1 + 144);
      if ( v10 )
        v11 = v10[6];
      else
        v11 = 0;
      result = DbgPrintEx(
                 0x7Fu,
                 3u,
                 "[%04x:%04x]CcWriteBehindInternal: PostProc:%d, Retry:%d, PVCM:%p(vid:%2lx)\n",
                 LODWORD(KeGetCurrentThread()[1].CycleTime),
                 KeGetCurrentThread()[1].CurrentRunTime,
                 (unsigned __int8)result,
                 HIBYTE(v24),
                 v10,
                 v11);
      v6 = HIBYTE(v24);
    }
    if ( v7 || !v6 )
      return result;
  }
  v8 = *(_DWORD **)(a1 + 144);
  if ( v8 )
    v9 = v8[6];
  else
    v9 = 0;
  return DbgPrintEx(
           0x7Fu,
           3u,
           "[%04x:%04x]CcWriteBehindInternal: WBPreProcess FAILED(%lx): PVCM:%p(vid:%2lx)\n",
           LODWORD(KeGetCurrentThread()[1].CycleTime),
           KeGetCurrentThread()[1].CurrentRunTime,
           1,
           v8,
           v9);
}

```

## disassembly

```asm
0x1402a1b30  push    rbp
0x1402a1b32  push    rbx
0x1402a1b33  push    rsi
0x1402a1b34  push    rdi
0x1402a1b35  push    r14
0x1402a1b37  lea     rbp, [rsp-70h]
0x1402a1b3c  sub     rsp, 170h
0x1402a1b43  mov     r14, [rcx+18h]
0x1402a1b47  mov     rbx, rcx
0x1402a1b4a  xor     edx, edx; Val
0x1402a1b4c  lea     rcx, [rsp+190h+var_130]; void *
0x1402a1b51  mov     r8d, 110h; Size
0x1402a1b57  call    memset_0
0x1402a1b5c  lea     rcx, [rsp+190h+var_130]
0x1402a1b61  mov     [rbp+90h+var_C0], r14
0x1402a1b65  mov     [rbp+90h+var_A8], 0
0x1402a1b6b  mov     [rbp+90h+var_28], rbx
0x1402a1b6f  mov     [rbp+90h+var_A5], 1
0x1402a1b73  call    CcWriteBehindPreProcess
0x1402a1b78  cmp     eax, 1
0x1402a1b7b  jz      loc_1402A1CEC
0x1402a1b81  mov     rax, [rbp+90h+var_D8]
0x1402a1b85  lea     rdi, [rsp+190h+var_140]
0x1402a1b8a  mov     rsi, [rsp+190h+var_118]
0x1402a1b8f  lea     rcx, CcNoDelay
0x1402a1b96  test    r14, r14
0x1402a1b99  mov     [rbp+90h+var_D0], rcx
0x1402a1b9d  xorps   xmm0, xmm0
0x1402a1ba0  mov     [rbp+90h+var_C8], 1
0x1402a1ba7  cmovnz  rdi, r14
0x1402a1bab  mov     [rbp+90h+var_C4], 0
0x1402a1baf  mov     [rbp+90h+var_C0], rdi
0x1402a1bb3  mov     [rsp+190h+var_118], rsi
0x1402a1bb8  mov     [rbp+90h+var_E8], 0
0x1402a1bc0  movups  [rsp+190h+var_140], xmm0
0x1402a1bc5  test    rax, rax
0x1402a1bc8  jz      short loc_1402A1BD9
0x1402a1bca  mov     rax, [rax]
0x1402a1bcd  mov     [rbp+90h+var_E0], rax
0x1402a1bd1  lea     rax, [rbp+90h+var_E0]
0x1402a1bd5  mov     [rbp+90h+var_D8], rax
0x1402a1bd9  lea     rcx, [rsp+190h+var_130]
0x1402a1bde  call    CcFlushCachePreProcess
0x1402a1be3  test    al, al
0x1402a1be5  jz      loc_1402A1C8B
0x1402a1beb  cmp     [rbp+90h+var_AC], 0
0x1402a1bef  jz      short loc_1402A1BF9
0x1402a1bf1  mov     [rbp+90h+var_D0], 0
0x1402a1bf9  mov     rax, [rsp+190h+var_120]
0x1402a1bfe  test    rax, rax
0x1402a1c01  jz      short loc_1402A1C40
0x1402a1c03  test    dword ptr [rax+98h], 4000000h
0x1402a1c0d  jnz     short loc_1402A1C40
0x1402a1c0f  lea     rcx, [rsp+190h+var_130]
0x1402a1c14  call    CcFlushCacheAcquireRange
0x1402a1c19  test    al, al
0x1402a1c1b  jz      short loc_1402A1C35
0x1402a1c1d  lea     rcx, [rsp+190h+var_130]
0x1402a1c22  call    CcFlushCacheOneRange
0x1402a1c27  lea     rcx, [rsp+190h+var_130]
0x1402a1c2c  call    CcFlushCachePostProcessOneRange
0x1402a1c31  test    al, al
0x1402a1c33  jnz     short loc_1402A1C0F
0x1402a1c35  cmp     [rbp+90h+var_48], 0
0x1402a1c3a  jnz     loc_1402A1CD2
0x1402a1c40  lea     rcx, [rsp+190h+var_130]
0x1402a1c45  call    CcFlushCachePostProcess
0x1402a1c4a  xor     edx, edx
0x1402a1c4c  lea     rcx, [rsp+190h+var_130]
0x1402a1c51  call    CcWriteBehindPostProcess
0x1402a1c56  movzx   ecx, byte ptr [rbp+90h+var_A8+1]
0x1402a1c5a  movzx   edi, al
0x1402a1c5d  test    al, al
0x1402a1c5f  jz      loc_1402A1D47
0x1402a1c65  test    cl, cl
0x1402a1c67  jnz     loc_1402A1D47
0x1402a1c6d  test    dil, dil
0x1402a1c70  jz      short loc_1402A1C81
0x1402a1c72  add     rsp, 170h
0x1402a1c79  pop     r14
0x1402a1c7b  pop     rdi
0x1402a1c7c  pop     rsi
0x1402a1c7d  pop     rbx
0x1402a1c7e  pop     rbp
0x1402a1c7f  retn
0x1402a1c81  test    cl, cl
0x1402a1c83  jnz     loc_1402A1B4A
0x1402a1c89  jmp     short loc_1402A1C72
0x1402a1c8b  mov     rcx, gs:188h
0x1402a1c94  lea     r8, a04x04xCcflushc; "[%04x:%04x]CcFlushCachePriv: PreProcess"...
0x1402a1c9b  mov     r9, gs:188h
0x1402a1ca4  mov     edx, 3; Level
0x1402a1ca9  mov     eax, [rdi]
0x1402a1cab  mov     dword ptr [rsp+190h+var_160], eax
0x1402a1caf  mov     eax, [rcx+510h]
0x1402a1cb5  mov     r9d, [r9+508h]
0x1402a1cbc  lea     ecx, [rdx+7Ch]; ComponentId
0x1402a1cbf  mov     [rsp+190h+var_168], rsi
0x1402a1cc4  mov     [rsp+190h+var_170], eax
0x1402a1cc8  call    DbgPrintEx
0x1402a1ccd  jmp     loc_1402A1C4A
0x1402a1cd2  cmp     [rbp+90h+var_38], 0
0x1402a1cd6  jz      loc_1402A1C40
0x1402a1cdc  xor     ecx, ecx; PerformanceFrequency
0x1402a1cde  call    KeQueryPerformanceCounter
0x1402a1ce3  mov     [rbp+90h+var_40], rax
0x1402a1ce7  jmp     loc_1402A1C40
0x1402a1cec  mov     rcx, [rbx+90h]
0x1402a1cf3  test    rcx, rcx
0x1402a1cf6  jnz     short loc_1402A1D60
0x1402a1cf8  xor     edx, edx
0x1402a1cfa  mov     rax, gs:188h
0x1402a1d03  lea     r8, a04x04xCcwriteb_1; "[%04x:%04x]CcWriteBehindInternal: WBPre"...
0x1402a1d0a  mov     r9, gs:188h
0x1402a1d13  mov     dword ptr [rsp+190h+var_158], edx
0x1402a1d17  mov     edx, 3; Level
0x1402a1d1c  mov     [rsp+190h+var_160], rcx
0x1402a1d21  mov     eax, [rax+510h]
0x1402a1d27  mov     r9d, [r9+508h]
0x1402a1d2e  lea     ecx, [rdx+7Ch]; ComponentId
0x1402a1d31  mov     dword ptr [rsp+190h+var_168], 1
0x1402a1d39  mov     [rsp+190h+var_170], eax
0x1402a1d3d  call    DbgPrintEx
0x1402a1d42  jmp     loc_1402A1C72
0x1402a1d47  mov     r8, [rbx+90h]
0x1402a1d4e  test    r8, r8
0x1402a1d51  jz      loc_140709C04
0x1402a1d57  mov     r10d, [r8+18h]
0x1402a1d5b  jmp     loc_140709C07
0x1402a1d60  mov     edx, [rcx+18h]
0x1402a1d63  jmp     short loc_1402A1CFA
0x140709c04  xor     r10d, r10d
0x140709c07  mov     rdx, gs:188h
0x140709c10  mov     r9, gs:188h
0x140709c19  mov     [rsp+190h+var_150], r10d
0x140709c1e  mov     [rsp+190h+var_158], r8
0x140709c23  lea     r8, a04x04xCcwriteb_4; "[%04x:%04x]CcWriteBehindInternal: PostP"...
0x140709c2a  mov     eax, [rdx+510h]
0x140709c30  mov     edx, 3; Level
0x140709c35  mov     r9d, [r9+508h]
0x140709c3c  mov     dword ptr [rsp+190h+var_160], ecx
0x140709c40  mov     dword ptr [rsp+190h+var_168], edi
0x140709c44  lea     ecx, [rdx+7Ch]; ComponentId
0x140709c47  mov     [rsp+190h+var_170], eax
0x140709c4b  call    DbgPrintEx
0x140709c50  mov     cl, byte ptr [rbp+90h+var_A8+1]
0x140709c53  jmp     loc_1402A1C6D
```
