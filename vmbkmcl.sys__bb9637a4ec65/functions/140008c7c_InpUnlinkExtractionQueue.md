# InpUnlinkExtractionQueue

- ea: `0x140008c7c`
- end: `0x140008d1a`
- name: `InpUnlinkExtractionQueue`
- size: `158`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400026f0`

## callees

- `0x140004860`
- `0x140005ae0`
- `0x140005ca0`
- `0x140008c7c`

## pseudocode

```c
void __fastcall InpUnlinkExtractionQueue(__int64 a1)
{
  _QWORD *v2; // rdi
  _QWORD *v3; // rdx
  __int64 v4; // rax
  _QWORD *v5; // rcx
  int v6; // ebx
  __int64 v7; // rdx
  unsigned int v8; // ebx

  v2 = (_QWORD *)(a1 + 1296);
  while ( 1 )
  {
    v3 = (_QWORD *)*v2;
    if ( (_QWORD *)*v2 == v2 )
      break;
    v4 = *v3;
    if ( *(_QWORD **)(*v3 + 8LL) != v3 || (v5 = (_QWORD *)v3[1], (_QWORD *)*v5 != v3) )
      __fastfail(3u);
    *v5 = v4;
    *(_QWORD *)(v4 + 8) = v5;
    if ( *((_WORD *)v3 + 8) == 6 || *((_WORD *)v3 + 8) == 7 || *((_WORD *)v3 + 8) == 9 )
    {
      v6 = *((_DWORD *)v3 - 24);
      v7 = (__int64)(v3 - 13);
      v8 = v6 - *(_DWORD *)(v7 + 12);
      InpFreePacket(a1, v7);
      InpPacketFreedLocked(a1, v8);
    }
    else if ( *((_WORD *)v3 + 8) == 11 )
    {
      OutCompletePacketToClient((__int64)(v3 - 22), 3221226166LL, 0);
    }
  }
}

```

## disassembly

```asm
0x140008c7c  mov     [rsp+arg_0], rbx
0x140008c81  mov     [rsp+arg_8], rsi
0x140008c86  push    rdi
0x140008c87  sub     rsp, 20h
0x140008c8b  mov     rsi, rcx
0x140008c8e  lea     rdi, [rcx+510h]
0x140008c95  mov     rdx, [rdi]
0x140008c98  cmp     rdx, rdi
0x140008c9b  jz      short loc_140008D09
0x140008c9d  mov     rax, [rdx]
0x140008ca0  cmp     [rax+8], rdx
0x140008ca4  jnz     short loc_140008D02
0x140008ca6  mov     rcx, [rdx+8]
0x140008caa  cmp     [rcx], rdx
0x140008cad  jnz     short loc_140008D02
0x140008caf  mov     [rcx], rax
0x140008cb2  mov     [rax+8], rcx
0x140008cb6  movzx   ecx, word ptr [rdx+10h]
0x140008cba  sub     ecx, 6
0x140008cbd  jz      short loc_140008CE4
0x140008cbf  sub     ecx, 1
0x140008cc2  jz      short loc_140008CE4
0x140008cc4  sub     ecx, 2
0x140008cc7  jz      short loc_140008CE4
0x140008cc9  cmp     ecx, 2
0x140008ccc  jnz     short loc_140008C95
0x140008cce  lea     rcx, [rdx-0B0h]
0x140008cd5  xor     r8d, r8d
0x140008cd8  mov     edx, 0C00002B6h
0x140008cdd  call    OutCompletePacketToClient
0x140008ce2  jmp     short loc_140008C95
0x140008ce4  mov     ebx, [rdx-60h]
0x140008ce7  add     rdx, 0FFFFFFFFFFFFFF98h
0x140008ceb  mov     rcx, rsi
0x140008cee  sub     ebx, [rdx+0Ch]
0x140008cf1  call    InpFreePacket
0x140008cf6  mov     edx, ebx
0x140008cf8  mov     rcx, rsi
0x140008cfb  call    InpPacketFreedLocked
0x140008d00  jmp     short loc_140008C95
0x140008d02  mov     ecx, 3
0x140008d07  int     29h; Win8: RtlFailFast(ecx)
0x140008d09  mov     rbx, [rsp+28h+arg_0]
0x140008d0e  mov     rsi, [rsp+28h+arg_8]
0x140008d13  add     rsp, 20h
0x140008d17  pop     rdi
0x140008d18  retn
```
