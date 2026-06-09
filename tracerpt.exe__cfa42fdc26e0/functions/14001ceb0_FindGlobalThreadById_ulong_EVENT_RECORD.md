# FindGlobalThreadById(ulong,_EVENT_RECORD *)

- ea: `0x14001ceb0`
- end: `0x14001cf7c`
- name: `?FindGlobalThreadById@@YAPEAU_THREAD_RECORD@@KPEAU_EVENT_RECORD@@@Z`
- size: `204`
- prototype: `struct _THREAD_RECORD *__fastcall(unsigned int, struct _EVENT_RECORD *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140003a30`
- `0x140005834`
- `0x140005acc`
- `0x140007658`
- `0x140007ec4`
- `0x140009ea8`
- `0x14000a0d4`

## callees

- `0x14001ceb0`

## pseudocode

```c
struct _THREAD_RECORD *__fastcall FindGlobalThreadById(unsigned int a1, struct _EVENT_RECORD *a2)
{
  __int64 v4; // r8
  __int64 *v5; // rdx
  unsigned int v6; // r9d
  __int64 *v7; // rcx
  UCHAR Opcode; // al
  __int64 **v10; // rax
  __int64 *v11; // rax

  v4 = qword_140082128 + 16LL * (a1 % 0x1D);
  v5 = *(__int64 **)v4;
  if ( *(_QWORD *)v4 == v4 )
    return 0;
  v6 = 0;
  while ( 1 )
  {
    v7 = (__int64 *)*v5;
    ++v6;
    if ( *((_DWORD *)v5 + 20) == a1 && (a1 || a2->BufferContext.ProcessorNumber == *((_DWORD *)v5 + 28)) )
      break;
    v5 = (__int64 *)*v5;
    if ( v7 == (__int64 *)v4 )
      return 0;
  }
  if ( *((_DWORD *)v5 + 27) )
  {
    if ( v5[22] != a2->EventHeader.TimeStamp.QuadPart )
    {
      if ( *(_QWORD *)&a2->EventHeader.ProviderId.Data1 != FileIoGuid )
        return 0;
      if ( *(_QWORD *)a2->EventHeader.ProviderId.Data4 != 0xE36404F80000F484uLL )
        return 0;
      Opcode = a2->EventHeader.EventDescriptor.Opcode;
      if ( Opcode )
      {
        if ( Opcode != 36 )
          return 0;
      }
    }
  }
  if ( v6 > 0x28 )
  {
    if ( (__int64 *)v7[1] != v5
      || (v10 = (__int64 **)v5[1], *v10 != v5)
      || (*v10 = v7, v7[1] = (__int64)v10, v11 = *(__int64 **)v4, *(_QWORD *)(*(_QWORD *)v4 + 8LL) != v4) )
    {
      __fastfail(3u);
    }
    *v5 = (__int64)v11;
    v5[1] = v4;
    v11[1] = (__int64)v5;
    *(_QWORD *)v4 = v5;
  }
  return (struct _THREAD_RECORD *)v5;
}

```

## disassembly

```asm
0x14001ceb0  mov     r10, rdx
0x14001ceb3  mov     r8d, ecx
0x14001ceb6  mov     eax, 8D3DCB09h
0x14001cebb  mov     r11d, ecx
0x14001cebe  mul     ecx
0x14001cec0  shr     edx, 4
0x14001cec3  imul    eax, edx, 1Dh
0x14001cec6  sub     r8d, eax
0x14001cec9  shl     r8, 4
0x14001cecd  add     r8, cs:qword_140082128
0x14001ced4  mov     rdx, [r8]
0x14001ced7  cmp     rdx, r8
0x14001ceda  jz      short loc_14001CF02
0x14001cedc  xor     r9d, r9d
0x14001cedf  mov     rcx, [rdx]
0x14001cee2  inc     r9d
0x14001cee5  cmp     [rdx+50h], r11d
0x14001cee9  jnz     short loc_14001CEFA
0x14001ceeb  test    r11d, r11d
0x14001ceee  jnz     short loc_14001CF05
0x14001cef0  movzx   eax, byte ptr [r10+50h]
0x14001cef5  cmp     eax, [rdx+70h]
0x14001cef8  jz      short loc_14001CF05
0x14001cefa  mov     rdx, rcx
0x14001cefd  cmp     rcx, r8
0x14001cf00  jnz     short loc_14001CEDF
0x14001cf02  xor     eax, eax
0x14001cf04  retn
0x14001cf05  cmp     dword ptr [rdx+6Ch], 0
0x14001cf09  jz      short loc_14001CF3E
0x14001cf0b  mov     rax, [r10+10h]
0x14001cf0f  cmp     [rdx+0B0h], rax
0x14001cf16  jz      short loc_14001CF3E
0x14001cf18  mov     rax, [r10+18h]
0x14001cf1c  cmp     rax, cs:FileIoGuid
0x14001cf23  jnz     short loc_14001CF02
0x14001cf25  mov     rax, [r10+20h]
0x14001cf29  cmp     rax, cs:qword_1400431C0
0x14001cf30  jnz     short loc_14001CF02
0x14001cf32  mov     al, [r10+2Dh]
0x14001cf36  test    al, al
0x14001cf38  jz      short loc_14001CF3E
0x14001cf3a  cmp     al, 24h ; '$'
0x14001cf3c  jnz     short loc_14001CF02
0x14001cf3e  cmp     r9d, 28h ; '('
0x14001cf42  jbe     short loc_14001CF71
0x14001cf44  cmp     [rcx+8], rdx
0x14001cf48  jnz     short loc_14001CF75
0x14001cf4a  mov     rax, [rdx+8]
0x14001cf4e  cmp     [rax], rdx
0x14001cf51  jnz     short loc_14001CF75
0x14001cf53  mov     [rax], rcx
0x14001cf56  mov     [rcx+8], rax
0x14001cf5a  mov     rax, [r8]
0x14001cf5d  cmp     [rax+8], r8
0x14001cf61  jnz     short loc_14001CF75
0x14001cf63  mov     [rdx], rax
0x14001cf66  mov     [rdx+8], r8
0x14001cf6a  mov     [rax+8], rdx
0x14001cf6e  mov     [r8], rdx
0x14001cf71  mov     rax, rdx
0x14001cf74  retn
0x14001cf75  mov     ecx, 3
0x14001cf7a  int     29h; Win8: RtlFailFast(ecx)
```
