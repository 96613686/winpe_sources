# ObjectTable<wmi::AutoRef<Object>>::AddToFreeList(ulong,ulong)

- ea: `0x180003604`
- end: `0x1800036f4`
- name: `?AddToFreeList@?$ObjectTable@V?$AutoRef@VObject@@@wmi@@@@AEAAXKK@Z`
- size: `240`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180003a2c`
- `0x180004510`

## callees

- `0x1800012d8`
- `0x18000262c`
- `0x180003604`
- `0x180003d78`

## pseudocode

```c
void __fastcall ObjectTable<wmi::AutoRef<Object>>::AddToFreeList(__int64 a1, int a2, unsigned int a3)
{
  __int64 v3; // r9
  unsigned int i; // edi
  __int64 v7; // rdx
  char v8; // si
  __int64 v9; // rbx
  __int64 v10; // rax
  LPVOID v11; // rax
  int v12; // ecx

  if ( a3 )
  {
    v3 = *((_QWORD *)&xmmword_180014A60 + 1);
    for ( i = 0; i < a3; ++i )
    {
      v7 = xmmword_180014A60;
      if ( (((_BYTE)xmmword_180014A60 + (_BYTE)v3) & 3) == 0
        && *((_QWORD *)&xmmword_180014A50 + 1) <= (unsigned __int64)(v3 + 4) >> 2 )
      {
        std::deque<unsigned long>::_Growmap(&qword_180014A48);
        v3 = *((_QWORD *)&xmmword_180014A60 + 1);
        v7 = xmmword_180014A60;
      }
      *(_QWORD *)&xmmword_180014A60 = (4LL * *((_QWORD *)&xmmword_180014A50 + 1) - 1) & v7;
      v8 = xmmword_180014A60 + v3;
      v9 = (*((_QWORD *)&xmmword_180014A50 + 1) - 1LL) & ((unsigned __int64)(xmmword_180014A60 + v3) >> 2);
      v10 = xmmword_180014A50;
      if ( !*(_QWORD *)(xmmword_180014A50 + 8 * v9) )
      {
        v11 = operator new(0x10u);
        if ( !v11 )
          std::_Xbad_alloc();
        *(_QWORD *)(xmmword_180014A50 + 8 * v9) = v11;
        v10 = xmmword_180014A50;
      }
      v12 = i + a2;
      *(_DWORD *)(*(_QWORD *)(v10 + 8 * v9) + 4LL * (v8 & 3)) = v12;
      v3 = ++*((_QWORD *)&xmmword_180014A60 + 1);
    }
  }
}

```

## disassembly

```asm
0x180003604  test    r8d, r8d
0x180003607  jz      locret_1800036ED
0x18000360d  push    rbx
0x18000360e  push    rbp
0x18000360f  push    rsi
0x180003610  push    rdi
0x180003611  push    r14
0x180003613  sub     rsp, 20h
0x180003617  mov     r9, qword ptr cs:xmmword_180014A60+8
0x18000361e  mov     ebp, r8d
0x180003621  mov     r14d, edx
0x180003624  xor     edi, edi
0x180003626  mov     rdx, qword ptr cs:xmmword_180014A60
0x18000362d  lea     eax, [rdx+r9]
0x180003631  test    al, 3
0x180003633  jnz     short loc_180003660
0x180003635  lea     rax, [r9+4]
0x180003639  shr     rax, 2
0x18000363d  cmp     qword ptr cs:xmmword_180014A50+8, rax
0x180003644  ja      short loc_180003660
0x180003646  lea     rcx, qword_180014A48
0x18000364d  call    ?_Growmap@?$deque@KV?$allocator@K@std@@@std@@IEAAX_K@Z; std::deque<ulong>::_Growmap(unsigned __int64)
0x180003652  mov     r9, qword ptr cs:xmmword_180014A60+8
0x180003659  mov     rdx, qword ptr cs:xmmword_180014A60
0x180003660  mov     rcx, qword ptr cs:xmmword_180014A50+8
0x180003667  lea     rax, ds:0FFFFFFFFFFFFFFFFh[rcx*4]
0x18000366f  and     rdx, rax
0x180003672  lea     rax, [rcx-1]
0x180003676  mov     qword ptr cs:xmmword_180014A60, rdx
0x18000367d  lea     rsi, [rdx+r9]
0x180003681  mov     rbx, rsi
0x180003684  shr     rbx, 2
0x180003688  and     rbx, rax
0x18000368b  mov     rax, qword ptr cs:xmmword_180014A50
0x180003692  cmp     qword ptr [rax+rbx*8], 0
0x180003697  jnz     short loc_1800036BA
0x180003699  mov     ecx, 10h; dwBytes
0x18000369e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800036a3  test    rax, rax
0x1800036a6  jz      short loc_1800036EE
0x1800036a8  mov     rcx, qword ptr cs:xmmword_180014A50
0x1800036af  mov     [rcx+rbx*8], rax
0x1800036b3  mov     rax, qword ptr cs:xmmword_180014A50
0x1800036ba  mov     rax, [rax+rbx*8]
0x1800036be  lea     ecx, [rdi+r14]
0x1800036c2  and     esi, 3
0x1800036c5  inc     edi
0x1800036c7  mov     [rax+rsi*4], ecx
0x1800036ca  mov     r9, qword ptr cs:xmmword_180014A60+8
0x1800036d1  inc     r9
0x1800036d4  mov     qword ptr cs:xmmword_180014A60+8, r9
0x1800036db  cmp     edi, ebp
0x1800036dd  jb      loc_180003626
0x1800036e3  add     rsp, 20h
0x1800036e7  pop     r14
0x1800036e9  pop     rdi
0x1800036ea  pop     rsi
0x1800036eb  pop     rbp
0x1800036ec  pop     rbx
0x1800036ed  retn
0x1800036ee  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
