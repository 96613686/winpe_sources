# CMcTpConstructor::ServerSecurePacket(CMemoryBuffer *)

- ea: `0x18001d4f4`
- end: `0x18001d558`
- name: `?ServerSecurePacket@CMcTpConstructor@@AEAAKPEAVCMemoryBuffer@@@Z`
- size: `100`
- prototype: `unsigned int __fastcall(CMcTpConstructor *__hidden this, struct CMemoryBuffer *)`
- caller_count: `10`
- callee_count: `5`
- tags: ``

## callers

- `0x1800132cc`
- `0x18001d560`
- `0x18001d730`
- `0x18001d8a8`
- `0x18001dab0`
- `0x18001dd2c`
- `0x18001df44`
- `0x18001e16c`
- `0x18001e398`
- `0x18001e73c`

## callees

- `0x18001d0d8`
- `0x18001d19c`
- `0x18001d358`
- `0x18001d4f4`
- `0x180025850`

## pseudocode

```c
__int64 __fastcall CMcTpConstructor::ServerSecurePacket(
        CMcTpConstructor *this,
        struct CMemoryBuffer *a2,
        __int64 a3,
        int a4)
{
  unsigned int v4; // ebx
  unsigned int v5; // eax
  __int64 v6; // rax

  v4 = 0;
  switch ( *((_WORD *)this + 1) )
  {
    case 0:
      v6 = *((_QWORD *)a2 + 5);
      *(_BYTE *)(v6 + 2) = 0;
      *(_WORD *)(v6 + 3) = 0;
      goto LABEL_11;
    case 1:
      v5 = CMcTpConstructor::HashPacket(this, a2, a3, a4);
      goto LABEL_9;
    case 2:
      v5 = CMcTpConstructor::SignPacket(this, a2, a3, a4);
      goto LABEL_9;
    case 3:
      v5 = CMcTpConstructor::ChecksumPacket(this, a2, a3, a4);
LABEL_9:
      v4 = v5;
LABEL_11:
      ElValidateWin32(v4, (const char *)a2, "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp", 0x482u);
      return v4;
  }
  return 13;
}

```

## disassembly

```asm
0x18001d4f4  push    rbx
0x18001d4f6  sub     rsp, 20h
0x18001d4fa  movzx   eax, word ptr [rcx+2]
0x18001d4fe  xor     ebx, ebx
0x18001d500  test    eax, eax
0x18001d502  jz      short loc_18001D531
0x18001d504  sub     eax, 1
0x18001d507  jz      short loc_18001D528
0x18001d509  sub     eax, 1
0x18001d50c  jz      short loc_18001D521
0x18001d50e  cmp     eax, 1
0x18001d511  jz      short loc_18001D51A
0x18001d513  mov     ebx, 0Dh
0x18001d518  jmp     short loc_18001D550
0x18001d51a  call    ?ChecksumPacket@CMcTpConstructor@@AEAAKPEAVCMemoryBuffer@@@Z; CMcTpConstructor::ChecksumPacket(CMemoryBuffer *)
0x18001d51f  jmp     short loc_18001D52D
0x18001d521  call    ?SignPacket@CMcTpConstructor@@AEAAKPEAVCMemoryBuffer@@@Z; CMcTpConstructor::SignPacket(CMemoryBuffer *)
0x18001d526  jmp     short loc_18001D52D
0x18001d528  call    ?HashPacket@CMcTpConstructor@@AEAAKPEAVCMemoryBuffer@@@Z; CMcTpConstructor::HashPacket(CMemoryBuffer *)
0x18001d52d  mov     ebx, eax
0x18001d52f  jmp     short loc_18001D53C
0x18001d531  mov     rax, [rdx+28h]
0x18001d535  mov     [rax+2], bl
0x18001d538  mov     [rax+3], bx
0x18001d53c  mov     r9d, 482h; unsigned int
0x18001d542  lea     r8, aBaseEcoWdsTran_17; "base\\eco\\wds\\transport\\lib\\mctpcon"...
0x18001d549  mov     ecx, ebx; unsigned int
0x18001d54b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001d550  mov     eax, ebx
0x18001d552  add     rsp, 20h
0x18001d556  pop     rbx
0x18001d557  retn
```
