# std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::count(_EVENT_DESCRIPTOR const &)

- ea: `0x180028f20`
- end: `0x180029053`
- name: `?count@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@QEBA_KAEBU_EVENT_DESCRIPTOR@@@Z`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180026640`

## callees

- `0x180028f20`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::count(
        __int64 **a1,
        __int16 *a2)
{
  __int64 *v2; // rax
  unsigned __int8 *v3; // rbx
  __int64 *v5; // r11
  __int64 *v6; // r8
  __int64 *v7; // r9
  unsigned __int16 v8; // di
  unsigned __int8 v9; // cl
  unsigned __int64 v10; // rcx
  unsigned __int16 v11; // dx
  __int64 v12; // r8
  __int64 *i; // rcx
  __int64 *v14; // rdx

  v2 = *a1;
  v3 = (unsigned __int8 *)(a2 + 1);
  v5 = *a1;
  v6 = (__int64 *)(*a1)[1];
  v7 = v6;
  if ( !*((_BYTE *)v6 + 25) )
  {
    v8 = *a2;
    do
    {
      if ( *((_WORD *)v7 + 16) < v8
        || *((_WORD *)v7 + 16) <= v8
        && ((v9 = *((_BYTE *)v7 + 34), v9 < *v3)
         || v9 <= *v3
         && ((v10 = v7[4], v10 < *(_QWORD *)a2) || v10 <= *(_QWORD *)a2 && (unsigned __int64)v7[5] < *((_QWORD *)a2 + 1))) )
      {
        v7 = (__int64 *)v7[2];
      }
      else
      {
        if ( *((_BYTE *)v5 + 25)
          && (v8 < *((_WORD *)v7 + 16)
           || *v3 < *((_BYTE *)v7 + 34)
           || *v3 <= *((_BYTE *)v7 + 34)
           && (*(_QWORD *)a2 < (unsigned __int64)v7[4]
            || *(_QWORD *)a2 <= (unsigned __int64)v7[4] && *((_QWORD *)a2 + 1) < (unsigned __int64)v7[5])) )
        {
          v5 = v7;
        }
        v2 = v7;
        v7 = (__int64 *)*v7;
      }
    }
    while ( !*((_BYTE *)v7 + 25) );
  }
  if ( !*((_BYTE *)v5 + 25) )
    v6 = (__int64 *)*v5;
  if ( !*((_BYTE *)v6 + 25) )
  {
    v11 = *a2;
    do
    {
      if ( v11 < *((_WORD *)v6 + 16)
        || v11 <= *((_WORD *)v6 + 16)
        && (*v3 < *((_BYTE *)v6 + 34)
         || *v3 <= *((_BYTE *)v6 + 34)
         && (*(_QWORD *)a2 < (unsigned __int64)v6[4]
          || *(_QWORD *)a2 <= (unsigned __int64)v6[4] && *((_QWORD *)a2 + 1) < (unsigned __int64)v6[5])) )
      {
        v5 = v6;
        v6 = (__int64 *)*v6;
      }
      else
      {
        v6 = (__int64 *)v6[2];
      }
    }
    while ( !*((_BYTE *)v6 + 25) );
  }
  v12 = 0;
  while ( v2 != v5 )
  {
    ++v12;
    if ( !*((_BYTE *)v2 + 25) )
    {
      i = (__int64 *)v2[2];
      if ( *((_BYTE *)i + 25) )
      {
        for ( i = (__int64 *)v2[1]; !*((_BYTE *)i + 25) && v2 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v2 = i;
LABEL_46:
        v2 = i;
      }
      else
      {
        v14 = (__int64 *)*i;
        if ( *(_BYTE *)(*i + 25) )
          goto LABEL_46;
        do
        {
          v2 = v14;
          v14 = (__int64 *)*v14;
        }
        while ( !*((_BYTE *)v14 + 25) );
      }
    }
  }
  return v12;
}

```

## disassembly

```asm
0x180028f20  push    rbx
0x180028f22  push    rsi
0x180028f23  push    rdi
0x180028f24  mov     rax, [rcx]
0x180028f27  lea     rbx, [rdx+2]
0x180028f2b  xor     esi, esi
0x180028f2d  mov     r10, rdx
0x180028f30  mov     r11, rax
0x180028f33  mov     r8, [rax+8]
0x180028f37  mov     r9, r8
0x180028f3a  cmp     [r8+19h], sil
0x180028f3e  jnz     short loc_180028FAC
0x180028f40  movzx   edi, word ptr [rdx]
0x180028f43  cmp     [r9+20h], di
0x180028f48  jb      short loc_180028FA2
0x180028f4a  ja      short loc_180028F6B
0x180028f4c  mov     cl, [r9+22h]
0x180028f50  cmp     cl, [rbx]
0x180028f52  jb      short loc_180028FA2
0x180028f54  ja      short loc_180028F6B
0x180028f56  mov     rcx, [r9+20h]
0x180028f5a  cmp     rcx, [rdx]
0x180028f5d  jb      short loc_180028FA2
0x180028f5f  ja      short loc_180028F6B
0x180028f61  mov     rcx, [rdx+8]
0x180028f65  cmp     [r9+28h], rcx
0x180028f69  jb      short loc_180028FA2
0x180028f6b  cmp     [r11+19h], sil
0x180028f6f  jz      short loc_180028F9A
0x180028f71  cmp     di, [r9+20h]
0x180028f76  jb      short loc_180028F97
0x180028f78  mov     al, [rbx]
0x180028f7a  cmp     al, [r9+22h]
0x180028f7e  jb      short loc_180028F97
0x180028f80  ja      short loc_180028F9A
0x180028f82  mov     rax, [rdx]
0x180028f85  cmp     rax, [r9+20h]
0x180028f89  jb      short loc_180028F97
0x180028f8b  ja      short loc_180028F9A
0x180028f8d  mov     rax, [r9+28h]
0x180028f91  cmp     [rdx+8], rax
0x180028f95  jnb     short loc_180028F9A
0x180028f97  mov     r11, r9
0x180028f9a  mov     rax, r9
0x180028f9d  mov     r9, [r9]
0x180028fa0  jmp     short loc_180028FA6
0x180028fa2  mov     r9, [r9+10h]
0x180028fa6  cmp     [r9+19h], sil
0x180028faa  jz      short loc_180028F43
0x180028fac  cmp     [r11+19h], sil
0x180028fb0  jnz     short loc_180028FB5
0x180028fb2  mov     r8, [r11]
0x180028fb5  cmp     [r8+19h], sil
0x180028fb9  jnz     short loc_180028FF8
0x180028fbb  movzx   edx, word ptr [rdx]
0x180028fbe  cmp     dx, [r8+20h]
0x180028fc3  jb      short loc_180028FEC
0x180028fc5  ja      short loc_180028FE6
0x180028fc7  mov     cl, [rbx]
0x180028fc9  cmp     cl, [r8+22h]
0x180028fcd  jb      short loc_180028FEC
0x180028fcf  ja      short loc_180028FE6
0x180028fd1  mov     rcx, [r10]
0x180028fd4  cmp     rcx, [r8+20h]
0x180028fd8  jb      short loc_180028FEC
0x180028fda  ja      short loc_180028FE6
0x180028fdc  mov     rcx, [r8+28h]
0x180028fe0  cmp     [r10+8], rcx
0x180028fe4  jb      short loc_180028FEC
0x180028fe6  mov     r8, [r8+10h]
0x180028fea  jmp     short loc_180028FF2
0x180028fec  mov     r11, r8
0x180028fef  mov     r8, [r8]
0x180028ff2  cmp     [r8+19h], sil
0x180028ff6  jz      short loc_180028FBE
0x180028ff8  mov     r8, rsi
0x180028ffb  cmp     rax, r11
0x180028ffe  jz      short loc_18002904B
0x180029000  inc     r8
0x180029003  cmp     [rax+19h], sil
0x180029007  jnz     short loc_180028FFB
0x180029009  mov     rcx, [rax+10h]
0x18002900d  cmp     [rcx+19h], sil
0x180029011  jnz     short loc_18002902D
0x180029013  mov     rdx, [rcx]
0x180029016  cmp     [rdx+19h], sil
0x18002901a  jnz     short loc_180029046
0x18002901c  mov     rcx, [rdx]
0x18002901f  mov     rax, rdx
0x180029022  mov     rdx, rcx
0x180029025  cmp     [rcx+19h], sil
0x180029029  jz      short loc_18002901C
0x18002902b  jmp     short loc_180028FFB
0x18002902d  mov     rcx, [rax+8]
0x180029031  jmp     short loc_180029040
0x180029033  cmp     rax, [rcx+10h]
0x180029037  jnz     short loc_180029046
0x180029039  mov     rax, rcx
0x18002903c  mov     rcx, [rcx+8]
0x180029040  cmp     [rcx+19h], sil
0x180029044  jz      short loc_180029033
0x180029046  mov     rax, rcx
0x180029049  jmp     short loc_180028FFB
0x18002904b  mov     rax, r8
0x18002904e  pop     rdi
0x18002904f  pop     rsi
0x180029050  pop     rbx
0x180029051  retn
```
