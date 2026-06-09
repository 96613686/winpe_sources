# YReader::ParsePi(void)

- ea: `0x1004083e0`
- end: `0x10040856e`
- name: `?ParsePi@YReader@@AEAAXXZ`
- size: `398`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x100404de0`
- `0x1004081e0`
- `0x100408980`
- `0x100408ba0`

## callees

- `0x100401780`
- `0x1004083e0`
- `0x100408580`
- `0x100415560`
- `0x1004394f0`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParsePi(YReader *this)
{
  unsigned int v2; // eax
  struct BlockAlloc::Header *v3; // rbx
  __int64 v4; // rdi
  void *v5; // rdx
  __int64 v6; // rcx
  struct BlockAlloc::Header *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r10
  __int64 v10; // r11
  __int16 v11; // cx
  __int16 v12; // r8
  __int16 v13; // cx
  __int16 v14; // r9
  __int128 v15; // xmm0
  void *Buf1[2]; // [rsp+20h] [rbp-18h] BYREF

  LODWORD(Buf1[1]) = 0;
  v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13));
  v3 = (struct BlockAlloc::Header *)*((_QWORD *)this + 55);
  v4 = v2;
  v5 = (void *)*((_QWORD *)v3 + 2);
  if ( *((_DWORD *)v3 + 6) - (int)v5 < v2 )
  {
    v6 = *((_QWORD *)v3 + 1);
    if ( v6 )
    {
      while ( 1 )
      {
        v3 = (struct BlockAlloc::Header *)v6;
        if ( *(_DWORD *)(v6 + 24) - (int)v6 - 32 >= v2 )
          break;
        v6 = *(_QWORD *)(v6 + 8);
        if ( !v6 )
          goto LABEL_5;
      }
      *(_QWORD *)(v6 + 16) = v6 + 32;
    }
    else
    {
LABEL_5:
      _mm_lfence();
      v7 = BlockAlloc::EnqueueBlock((YReader *)((char *)this + 416), v2, v3);
      *((_QWORD *)v3 + 1) = v7;
      v3 = v7;
    }
    *((_QWORD *)this + 55) = v3;
    v5 = (void *)*((_QWORD *)v3 + 2);
  }
  *((_QWORD *)v3 + 2) += v4;
  v8 = *((_QWORD *)this + 13);
  Buf1[0] = v5;
  (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v8 + 104LL))(v8, Buf1);
  if ( LODWORD(Buf1[1]) == dword_100450B78 )
  {
    v9 = CodeStringPtr::xml;
    v10 = (unsigned int)dword_100450B78;
    if ( !dword_100450B78 )
      goto LABEL_25;
    do
    {
      v11 = *(_WORD *)((char *)Buf1[0] + v9 - CodeStringPtr::xml);
      v9 += 2;
      v12 = v11 + 32;
      if ( (unsigned __int16)(v11 - 65) > 0x19u )
        v12 = v11;
      v13 = *(_WORD *)(v9 - 2);
      v14 = v13 + 32;
      if ( (unsigned __int16)(v13 - 65) > 0x19u )
        v14 = *(_WORD *)(v9 - 2);
      --v10;
    }
    while ( v10 && v12 && v12 == v14 );
    if ( v12 == v14 )
    {
LABEL_25:
      if ( memcmp(Buf1[0], CodeStringPtr::xml, 2LL * (unsigned int)dword_100450B78) )
      {
        MXRRaiseException(-1072894402);
        JUMPOUT(0x10040856DLL);
      }
      MXRRaiseException(-1072894403);
      __debugbreak();
    }
  }
  v15 = *(_OWORD *)Buf1;
  *((_DWORD *)this + 444) = 9;
  *((_OWORD *)this + 101) = v15;
  YReader::ParsePiData(this);
}

```

## disassembly

```asm
0x1004083e0  mov     [rsp+arg_8], rbx
0x1004083e5  mov     [rsp+arg_10], rbp
0x1004083ea  mov     [rsp+arg_18], rsi
0x1004083ef  push    rdi
0x1004083f0  sub     rsp, 30h
0x1004083f4  mov     rsi, rcx
0x1004083f7  mov     dword ptr [rsp+38h+Buf1+8], 0
0x1004083ff  mov     rcx, [rcx+68h]
0x100408403  mov     rax, [rcx]
0x100408406  mov     rax, [rax+60h]
0x10040840a  call    cs:__guard_dispatch_icall_fptr
0x100408410  mov     rbx, [rsi+1B8h]
0x100408417  mov     edi, eax
0x100408419  mov     rdx, [rbx+10h]
0x10040841d  mov     ecx, [rbx+18h]
0x100408420  sub     ecx, edx
0x100408422  cmp     ecx, eax
0x100408424  jnb     short loc_100408472
0x100408426  mov     rcx, [rbx+8]
0x10040842a  test    rcx, rcx
0x10040842d  jz      short loc_10040844C
0x10040842f  nop
0x100408430  mov     eax, [rcx+18h]
0x100408433  mov     rbx, rcx
0x100408436  sub     eax, ecx
0x100408438  sub     eax, 20h ; ' '
0x10040843b  cmp     eax, edi
0x10040843d  jnb     loc_100408518
0x100408443  mov     rcx, [rcx+8]
0x100408447  test    rcx, rcx
0x10040844a  jnz     short loc_100408430
0x10040844c  lfence
0x10040844f  mov     r8, rbx; struct BlockAlloc::Header *
0x100408452  lea     rcx, [rsi+1A0h]; this
0x100408459  mov     edx, edi; unsigned int
0x10040845b  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x100408460  mov     [rbx+8], rax
0x100408464  mov     rbx, rax
0x100408467  mov     [rsi+1B8h], rbx
0x10040846e  mov     rdx, [rbx+10h]
0x100408472  add     [rbx+10h], rdi
0x100408476  mov     rcx, [rsi+68h]
0x10040847a  mov     [rsp+38h+Buf1], rdx
0x10040847f  lea     rdx, [rsp+38h+Buf1]
0x100408484  mov     rax, [rcx]
0x100408487  mov     rax, [rax+68h]
0x10040848b  call    cs:__guard_dispatch_icall_fptr
0x100408491  mov     eax, cs:dword_100450B78
0x100408497  cmp     dword ptr [rsp+38h+Buf1+8], eax
0x10040849b  jnz     loc_100408525
0x1004084a1  mov     rdx, cs:?xml@CodeStringPtr@@2UStringPtr@@A; Buf2
0x1004084a8  mov     edi, eax
0x1004084aa  mov     rbp, [rsp+38h+Buf1]
0x1004084af  mov     r10, rdx
0x1004084b2  mov     r11d, eax
0x1004084b5  test    eax, eax
0x1004084b7  jz      short loc_100408506
0x1004084b9  mov     rbx, rbp
0x1004084bc  sub     rbx, rdx
0x1004084bf  nop
0x1004084c0  movzx   ecx, word ptr [rbx+r10]
0x1004084c5  lea     r10, [r10+2]
0x1004084c9  lea     eax, [rcx-41h]
0x1004084cc  cmp     ax, 19h
0x1004084d0  lea     r8d, [rcx+20h]
0x1004084d4  cmova   r8w, cx
0x1004084d9  movzx   ecx, word ptr [r10-2]
0x1004084de  lea     eax, [rcx-41h]
0x1004084e1  cmp     ax, 19h
0x1004084e5  lea     r9d, [rcx+20h]
0x1004084e9  cmova   r9w, cx
0x1004084ee  sub     r11, 1
0x1004084f2  jz      short loc_100408500
0x1004084f4  test    r8w, r8w
0x1004084f8  jz      short loc_100408500
0x1004084fa  cmp     r8w, r9w
0x1004084fe  jz      short loc_1004084C0
0x100408500  cmp     r8w, r9w
0x100408504  jnz     short loc_100408525
0x100408506  lea     r8, [rdi+rdi]; Size
0x10040850a  mov     rcx, rbp; Buf1
0x10040850d  call    memcmp
0x100408512  test    eax, eax
0x100408514  jz      short loc_100408558
0x100408516  jmp     short loc_100408563
0x100408518  lea     rax, [rcx+20h]
0x10040851c  mov     [rcx+10h], rax
0x100408520  jmp     loc_100408467
0x100408525  movups  xmm0, xmmword ptr [rsp+38h+Buf1]
0x10040852a  mov     rcx, rsi; this
0x10040852d  mov     dword ptr [rsi+6F0h], 9
0x100408537  movups  xmmword ptr [rsi+650h], xmm0
0x10040853e  call    ?ParsePiData@YReader@@AEAAXXZ; YReader::ParsePiData(void)
0x100408543  mov     rbx, [rsp+38h+arg_8]
0x100408548  mov     rbp, [rsp+38h+arg_10]
0x10040854d  mov     rsi, [rsp+38h+arg_18]
0x100408552  add     rsp, 30h
0x100408556  pop     rdi
0x100408557  retn
0x100408558  mov     ecx, 0C00CEE3Dh; int
0x10040855d  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100408562  int     3; Trap to Debugger
0x100408563  mov     ecx, 0C00CEE3Eh; int
0x100408568  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
