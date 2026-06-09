# CASFArchive::StoreGUID(_GUID const &)

- ea: `0x180026748`
- end: `0x1800267a8`
- name: `?StoreGUID@CASFArchive@@QEAAJAEBU_GUID@@@Z`
- size: `96`
- prototype: `__int64 __fastcall(CASFArchive *__hidden this, const struct _GUID *)`
- caller_count: `15`
- callee_count: `4`
- tags: ``

## callers

- `0x18001da90`
- `0x18001dc30`
- `0x18001dce0`
- `0x18001de50`
- `0x18001e3d0`
- `0x18001e440`
- `0x18001e640`
- `0x18001e790`
- `0x18001e900`
- `0x18001e9c0`
- `0x18001ea80`
- `0x18001ebb0`
- `0x18001ecf0`
- `0x18001efa0`
- `0x18001f0c0`

## callees

- `0x18002658c`
- `0x1800266d8`
- `0x180026748`
- `0x180026824`

## pseudocode

```c
__int64 __fastcall CASFArchive::StoreGUID(CASFArchive *this, const struct _GUID *a2)
{
  __int64 result; // rax
  __int64 v3; // r10
  CASFArchive *v4; // r11
  __int64 v5; // r10
  CASFArchive *v6; // r11
  __int64 v7; // r10
  CASFArchive *v8; // r11
  int i; // r9d
  int v10; // r9d

  result = CASFArchive::StoreDWORD(this, a2->Data1);
  if ( (int)result >= 0 )
  {
    result = CASFArchive::StoreWORD(v4, *(_WORD *)(v3 + 4));
    if ( (int)result >= 0 )
    {
      result = CASFArchive::StoreWORD(v6, *(_WORD *)(v5 + 6));
      if ( (int)result >= 0 )
      {
        for ( i = 0; i < 8; i = v10 + 1 )
        {
          result = CASFArchive::StoreBYTE(v8, *(_BYTE *)(i + v7 + 8));
          if ( (int)result < 0 )
            return result;
        }
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180026748  sub     rsp, 28h
0x18002674c  mov     r10, rdx
0x18002674f  mov     r11, rcx
0x180026752  mov     edx, [rdx]; unsigned int
0x180026754  call    ?StoreDWORD@CASFArchive@@QEAAJK@Z; CASFArchive::StoreDWORD(ulong)
0x180026759  test    eax, eax
0x18002675b  js      short loc_1800267A3
0x18002675d  movzx   edx, word ptr [r10+4]; unsigned __int16
0x180026762  mov     rcx, r11; this
0x180026765  call    ?StoreWORD@CASFArchive@@QEAAJG@Z; CASFArchive::StoreWORD(ushort)
0x18002676a  test    eax, eax
0x18002676c  js      short loc_1800267A3
0x18002676e  movzx   edx, word ptr [r10+6]; unsigned __int16
0x180026773  mov     rcx, r11; this
0x180026776  call    ?StoreWORD@CASFArchive@@QEAAJG@Z; CASFArchive::StoreWORD(ushort)
0x18002677b  test    eax, eax
0x18002677d  js      short loc_1800267A3
0x18002677f  xor     r9d, r9d
0x180026782  cmp     r9d, 8
0x180026786  jge     short loc_1800267A1
0x180026788  movsxd  rdx, r9d
0x18002678b  mov     rcx, r11; this
0x18002678e  mov     dl, [rdx+r10+8]; unsigned __int8
0x180026793  call    ?StoreBYTE@CASFArchive@@QEAAJE@Z; CASFArchive::StoreBYTE(uchar)
0x180026798  test    eax, eax
0x18002679a  js      short loc_1800267A3
0x18002679c  inc     r9d
0x18002679f  jmp     short loc_180026782
0x1800267a1  xor     eax, eax
0x1800267a3  add     rsp, 28h
0x1800267a7  retn
```
