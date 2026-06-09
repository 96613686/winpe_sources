# GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)

- ea: `0x140004c2c`
- end: `0x140004ca6`
- name: `?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z`
- size: `122`
- prototype: `__int64 __fastcall(PEVENT_RECORD Event, unsigned __int16 *, BYTE *, unsigned int *)`
- caller_count: `26`
- callee_count: `4`
- tags: ``

## callers

- `0x1400032c0`
- `0x140003a30`
- `0x140005834`
- `0x140005914`
- `0x140005acc`
- `0x140006588`
- `0x1400069c8`
- `0x140006db8`
- `0x140006f6c`
- `0x140007658`
- `0x1400078ec`
- `0x140007ec4`
- `0x140008444`
- `0x140008588`
- `0x140008788`
- `0x140008988`
- `0x140008b40`
- `0x140008c50`
- `0x140008d14`
- `0x140009258`
- `0x140009880`
- `0x140009d78`
- `0x140009ea8`
- `0x14000a0d4`
- `0x14000a3a4`
- `0x14001e570`

## callees

- `0x140004c2c`
- `0x140004cac`
- `0x140004f08`
- `0x14000556c`

## pseudocode

```c
__int64 __fastcall GetMofData(PEVENT_RECORD Event, unsigned __int16 *a2, BYTE *a3, unsigned int *a4)
{
  struct _MOF_INFO *MofInfoHead; // rax
  struct _MOF_VERSION *MofVersion; // rax

  if ( !Event || !a4 )
    return 87;
  MofInfoHead = GetMofInfoHead(&Event->EventHeader.ProviderId);
  if ( !MofInfoHead )
    return 8;
  MofVersion = GetMofVersion(Event, MofInfoHead, 0);
  if ( !MofVersion )
    return 8;
  if ( *((_QWORD *)MofVersion + 2) )
    return GetProperty(Event, a3);
  return 1168;
}

```

## disassembly

```asm
0x140004c2c  push    rbx
0x140004c2e  push    rbp
0x140004c2f  push    rsi
0x140004c30  push    rdi
0x140004c31  sub     rsp, 38h
0x140004c35  mov     rdi, r9
0x140004c38  mov     rsi, r8
0x140004c3b  mov     rbp, rdx
0x140004c3e  mov     rbx, rcx
0x140004c41  test    rcx, rcx
0x140004c44  jz      short loc_140004C98
0x140004c46  test    r9, r9
0x140004c49  jz      short loc_140004C98
0x140004c4b  add     rcx, 18h; struct _GUID *
0x140004c4f  call    ?GetMofInfoHead@@YAPEAU_MOF_INFO@@PEBU_GUID@@@Z; GetMofInfoHead(_GUID const *)
0x140004c54  test    rax, rax
0x140004c57  jz      short loc_140004C91
0x140004c59  xor     r8d, r8d; unsigned __int8
0x140004c5c  mov     rdx, rax; struct _MOF_INFO *
0x140004c5f  mov     rcx, rbx; Event
0x140004c62  call    ?GetMofVersion@@YAPEAU_MOF_VERSION@@PEAU_EVENT_RECORD@@PEAU_MOF_INFO@@E@Z; GetMofVersion(_EVENT_RECORD *,_MOF_INFO *,uchar)
0x140004c67  test    rax, rax
0x140004c6a  jz      short loc_140004C91
0x140004c6c  mov     rdx, [rax+10h]
0x140004c70  test    rdx, rdx
0x140004c73  jnz     short loc_140004C7C
0x140004c75  mov     eax, 490h
0x140004c7a  jmp     short loc_140004C9D
0x140004c7c  mov     r9, rdi
0x140004c7f  mov     [rsp+58h+var_38], rsi; PBYTE
0x140004c84  mov     r8, rbp
0x140004c87  mov     rcx, rbx; pEvent
0x140004c8a  call    GetProperty
0x140004c8f  jmp     short loc_140004C9D
0x140004c91  mov     eax, 8
0x140004c96  jmp     short loc_140004C9D
0x140004c98  mov     eax, 57h ; 'W'
0x140004c9d  add     rsp, 38h
0x140004ca1  pop     rdi
0x140004ca2  pop     rsi
0x140004ca3  pop     rbp
0x140004ca4  pop     rbx
0x140004ca5  retn
```
