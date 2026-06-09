# CWMFileSinkV1::CWMFileSinkV1(long *,CTPtrArray<WRITER_SINK_CALLBACK,20> *)

- ea: `0x1800078c0`
- end: `0x180007bac`
- name: `??0CWMFileSinkV1@@QEAA@PEAJPEAV?$CTPtrArray@UWRITER_SINK_CALLBACK@@$0BE@@@@Z`
- size: `748`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001f94`

## callees

- `0x180001f1c`
- `0x1800078c0`
- `0x1800291f4`

## pseudocode

```c
__int64 __fastcall CWMFileSinkV1::CWMFileSinkV1(__int64 a1, int *a2)
{
  __int64 v2; // rbx
  Mutex *v3; // rbp
  int v6; // eax
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax

  *(_QWORD *)(a1 + 16) = 1;
  *(_QWORD *)(a1 + 24) = 0;
  v2 = a1 + 9008;
  *(_QWORD *)(a1 + 36) = 0;
  v3 = (Mutex *)(a1 + 144);
  *(_QWORD *)a1 = &CWMFileSinkV1::`vftable'{for `IWMWriterFileSink3'};
  *(_QWORD *)(a1 + 8) = &CWMFileSinkV1::`vftable'{for `IWMRegisterCallback'};
  *(_DWORD *)(a1 + 88) = 0;
  *(_DWORD *)(a1 + 136) = 0;
  *(_DWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 192) = -1;
  *(_QWORD *)(a1 + 296) = -1;
  *(_QWORD *)(a1 + 200) = 0;
  *(_DWORD *)(a1 + 208) = 128;
  *(_DWORD *)(a1 + 212) = 1;
  *(_QWORD *)(a1 + 216) = 2;
  *(_DWORD *)(a1 + 224) = 0;
  *(_QWORD *)(a1 + 232) = 0;
  *(_QWORD *)(a1 + 240) = 0;
  *(_QWORD *)(a1 + 256) = 0;
  *(_QWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 272) = 0;
  *(_DWORD *)(a1 + 280) = 0;
  *(_QWORD *)(a1 + 288) = 0;
  *(_QWORD *)(a1 + 312) = 0;
  *(_QWORD *)(a1 + 320) = 0;
  *(_QWORD *)(a1 + 328) = 0;
  *(_QWORD *)(a1 + 336) = 0;
  *(_WORD *)(a1 + 3416) = -1;
  *(_QWORD *)(a1 + 7360) = 0;
  *(_WORD *)(a1 + 8392) = 0;
  *(_QWORD *)(a1 + 8400) = 0;
  *(_DWORD *)(a1 + 8408) = 1;
  *(_QWORD *)(a1 + 8416) = 0;
  *(_QWORD *)(a1 + 8456) = 0;
  *(_QWORD *)(a1 + 8464) = 0;
  *(_DWORD *)(a1 + 8472) = 0;
  *(_QWORD *)(a1 + 8440) = 0;
  *(_QWORD *)(a1 + 8432) = 0;
  *(_QWORD *)(a1 + 8424) = 0;
  *(_DWORD *)(a1 + 8448) = 0;
  *(_WORD *)(a1 + 9000) = 0;
  *(_QWORD *)(a1 + 9016) = 0;
  *(_WORD *)(a1 + 9032) = 0;
  *(_BYTE *)(a1 + 9034) = 0;
  memset_0((void *)(a1 + 9040), 0, 0xA0u);
  *(_DWORD *)(v2 + 12) |= 1u;
  *(_QWORD *)v2 = &CTPtrArray<CASFStreamPropertiesObjectEx::_STREAM_NAME_RECORD,20>::`vftable';
  *(_QWORD *)(v2 + 192) = 0;
  *(_QWORD *)(v2 + 200) = v2;
  *(_DWORD *)(v2 + 208) = 0;
  *(_DWORD *)(v2 + 216) = 0;
  *(_QWORD *)(v2 + 16) = 0;
  *(_QWORD *)(a1 + 9248) = 0;
  *(_DWORD *)(a1 + 9256) = 0;
  *(_QWORD *)(a1 + 9264) = 0;
  *(_QWORD *)(a1 + 9240) = 0;
  v6 = Mutex::Init((Mutex *)(a1 + 96));
  if ( v6 < 0 || (v6 = Mutex::Init(v3), v6 < 0) || (v6 = Mutex::Init((Mutex *)(a1 + 48)), v6 < 0) )
  {
    if ( a2 )
      *a2 = v6;
  }
  else
  {
    if ( a2 )
      *a2 = v6;
    *(_DWORD *)(a1 + 32) = 0;
    *(_QWORD *)(a1 + 8464) = a1 + 8476;
    v7 = 0;
    *(_DWORD *)(a1 + 8472) = 16;
    *(_QWORD *)(a1 + 8476) = 0;
    do
    {
      v8 = 32 * v7++;
      v9 = v8 + *(_QWORD *)(a1 + 8464) + 8LL;
      *(_QWORD *)(v9 + 16) = *(_QWORD *)(a1 + 8456);
      *(_QWORD *)(a1 + 8456) = v9;
    }
    while ( v7 != 16 );
    memset_0((void *)(a1 + 344), 0, 0xC00u);
    memset_0((void *)(a1 + 7368), 0, 0x200u);
    memset_0((void *)(a1 + 7880), 0, 0x200u);
    memset_0((void *)(a1 + 3520), 0, 0xC00u);
    memset_0((void *)(a1 + 3424), 0, 0x60u);
    v10 = 0;
    *(_DWORD *)(a1 + 9232) = 1;
    *(_WORD *)(a1 + 9000) = 0;
    do
    {
      v11 = 3 * v10++;
      *(_DWORD *)(a1 + 16 * v11 + 388) = 0;
    }
    while ( v10 != 64 );
  }
  return a1;
}

```

## disassembly

```asm
0x1800078c0  push    rbx
0x1800078c2  push    rbp
0x1800078c3  push    rsi
0x1800078c4  push    rdi
0x1800078c5  push    r12
0x1800078c7  push    r14
0x1800078c9  push    r15
0x1800078cb  sub     rsp, 20h
0x1800078cf  xor     r12d, r12d
0x1800078d2  mov     qword ptr [rcx+10h], 1
0x1800078da  mov     [rcx+18h], r12
0x1800078de  lea     rbx, [rcx+2330h]
0x1800078e5  mov     [rcx+24h], r12
0x1800078e9  lea     rbp, [rcx+90h]
0x1800078f0  lea     rax, ??_7CWMFileSinkV1@@6BIWMWriterFileSink3@@@; const CWMFileSinkV1::`vftable'{for `IWMWriterFileSink3'}
0x1800078f7  mov     r14, rdx
0x1800078fa  mov     [rcx], rax
0x1800078fd  mov     rsi, rcx
0x180007900  lea     rax, ??_7CWMFileSinkV1@@6BIWMRegisterCallback@@@; const CWMFileSinkV1::`vftable'{for `IWMRegisterCallback'}
0x180007907  xor     edx, edx; Val
0x180007909  mov     [rcx+8], rax
0x18000790d  mov     r8d, 0A0h; Size
0x180007913  mov     [rcx+58h], r12d
0x180007917  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000791b  mov     [rcx+88h], r12d
0x180007922  mov     [rbp+28h], r12d
0x180007926  mov     [rcx+0C0h], rax
0x18000792d  mov     [rcx+128h], rax
0x180007934  xor     eax, eax
0x180007936  mov     [rcx+0C8h], r12
0x18000793d  mov     dword ptr [rcx+0D0h], 80h
0x180007947  mov     dword ptr [rcx+0D4h], 1
0x180007951  mov     qword ptr [rcx+0D8h], 2
0x18000795c  mov     [rcx+0E0h], r12d
0x180007963  mov     [rcx+0E8h], r12
0x18000796a  mov     [rcx+0F0h], r12
0x180007971  mov     [rcx+100h], r12
0x180007978  mov     [rcx+108h], r12
0x18000797f  mov     [rcx+110h], r12
0x180007986  mov     [rcx+118h], r12d
0x18000798d  mov     [rcx+120h], r12
0x180007994  mov     [rcx+138h], r12
0x18000799b  mov     [rcx+140h], r12
0x1800079a2  mov     [rcx+148h], r12
0x1800079a9  mov     [rcx+150h], r12
0x1800079b0  mov     word ptr [rcx+0D58h], 0FFFFh
0x1800079b9  mov     [rcx+1CC0h], r12
0x1800079c0  mov     [rcx+20C8h], r12w
0x1800079c8  mov     [rcx+20D0h], r12
0x1800079cf  mov     dword ptr [rcx+20D8h], 1
0x1800079d9  mov     [rcx+20E0h], r12
0x1800079e0  mov     [rcx+2108h], r12
0x1800079e7  mov     [rcx+2110h], r12
0x1800079ee  mov     [rcx+2118h], r12d
0x1800079f5  mov     [rcx+20F8h], r12
0x1800079fc  mov     [rcx+20F0h], r12
0x180007a03  mov     [rcx+20E8h], r12
0x180007a0a  mov     [rcx+2100h], r12d
0x180007a11  mov     [rcx+2328h], r12w
0x180007a19  lea     rcx, [rbx+20h]; void *
0x180007a1d  mov     [rbx+8], r12
0x180007a21  mov     [rbx+18h], ax
0x180007a25  mov     [rbx+1Ah], al
0x180007a28  call    memset_0
0x180007a2d  or      dword ptr [rbx+0Ch], 1
0x180007a31  lea     rax, ??_7?$CTPtrArray@U_STREAM_NAME_RECORD@CASFStreamPropertiesObjectEx@@$0BE@@@6B@; const CTPtrArray<CASFStreamPropertiesObjectEx::_STREAM_NAME_RECORD,20>::`vftable'
0x180007a38  mov     [rbx], rax
0x180007a3b  lea     rcx, [rsi+60h]; this
0x180007a3f  mov     [rbx+0C0h], r12
0x180007a46  mov     [rbx+0C8h], rbx
0x180007a4d  mov     [rbx+0D0h], r12d
0x180007a54  mov     [rbx+0D8h], r12d
0x180007a5b  mov     [rbx+10h], r12
0x180007a5f  mov     [rsi+2420h], r12
0x180007a66  mov     [rsi+2428h], r12d
0x180007a6d  mov     [rsi+2430h], r12
0x180007a74  mov     [rsi+2418h], r12
0x180007a7b  call    ?Init@Mutex@@QEAAJXZ; Mutex::Init(void)
0x180007a80  test    eax, eax
0x180007a82  js      loc_180007B92
0x180007a88  mov     rcx, rbp; this
0x180007a8b  call    ?Init@Mutex@@QEAAJXZ; Mutex::Init(void)
0x180007a90  test    eax, eax
0x180007a92  js      loc_180007B92
0x180007a98  lea     rcx, [rsi+30h]; this
0x180007a9c  call    ?Init@Mutex@@QEAAJXZ; Mutex::Init(void)
0x180007aa1  test    eax, eax
0x180007aa3  js      loc_180007B92
0x180007aa9  test    r14, r14
0x180007aac  jz      short loc_180007AB1
0x180007aae  mov     [r14], eax
0x180007ab1  mov     [rsi+20h], r12d
0x180007ab5  lea     rax, [rsi+211Ch]
0x180007abc  mov     [rsi+2110h], rax
0x180007ac3  mov     r8, r12
0x180007ac6  mov     dword ptr [rsi+2118h], 10h
0x180007ad0  mov     [rax], r12
0x180007ad3  mov     rdx, [rsi+2110h]
0x180007ada  mov     rcx, r8
0x180007add  mov     rax, [rsi+2108h]
0x180007ae4  add     rdx, 8
0x180007ae8  shl     rcx, 5
0x180007aec  inc     r8
0x180007aef  add     rdx, rcx
0x180007af2  mov     [rdx+10h], rax
0x180007af6  mov     [rsi+2108h], rdx
0x180007afd  cmp     r8, 10h
0x180007b01  jnz     short loc_180007AD3
0x180007b03  mov     edi, 0C00h
0x180007b08  lea     rcx, [rsi+158h]; void *
0x180007b0f  mov     r8d, edi; Size
0x180007b12  xor     edx, edx; Val
0x180007b14  call    memset_0
0x180007b19  mov     ebx, 200h
0x180007b1e  lea     rcx, [rsi+1CC8h]; void *
0x180007b25  mov     r8d, ebx; Size
0x180007b28  xor     edx, edx; Val
0x180007b2a  call    memset_0
0x180007b2f  lea     rcx, [rsi+1EC8h]; void *
0x180007b36  mov     r8d, ebx; Size
0x180007b39  xor     edx, edx; Val
0x180007b3b  call    memset_0
0x180007b40  lea     rcx, [rsi+0DC0h]; void *
0x180007b47  mov     r8d, edi; Size
0x180007b4a  xor     edx, edx; Val
0x180007b4c  call    memset_0
0x180007b51  xor     edx, edx; Val
0x180007b53  lea     rcx, [rsi+0D60h]; void *
0x180007b5a  lea     r8d, [rdx+60h]; Size
0x180007b5e  call    memset_0
0x180007b63  mov     rcx, r12
0x180007b66  mov     dword ptr [rsi+2410h], 1
0x180007b70  mov     [rsi+2328h], r12w
0x180007b78  lea     rax, [rcx+rcx*2]
0x180007b7c  inc     rcx
0x180007b7f  add     rax, rax
0x180007b82  mov     [rsi+rax*8+184h], r12d
0x180007b8a  cmp     rcx, 40h ; '@'
0x180007b8e  jnz     short loc_180007B78
0x180007b90  jmp     short loc_180007B9A
0x180007b92  test    r14, r14
0x180007b95  jz      short loc_180007B9A
0x180007b97  mov     [r14], eax
0x180007b9a  mov     rax, rsi
0x180007b9d  add     rsp, 20h
0x180007ba1  pop     r15
0x180007ba3  pop     r14
0x180007ba5  pop     r12
0x180007ba7  pop     rdi
0x180007ba8  pop     rsi
0x180007ba9  pop     rbp
0x180007baa  pop     rbx
0x180007bab  retn
```
