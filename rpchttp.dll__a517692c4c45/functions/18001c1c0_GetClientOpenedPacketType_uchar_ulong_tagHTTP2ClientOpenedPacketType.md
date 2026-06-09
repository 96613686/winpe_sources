# GetClientOpenedPacketType(uchar *,ulong,tagHTTP2ClientOpenedPacketType *)

- ea: `0x18001c1c0`
- end: `0x18001c262`
- name: `?GetClientOpenedPacketType@@YAJPEAEKPEAW4tagHTTP2ClientOpenedPacketType@@@Z`
- size: `162`
- prototype: `__int64 __fastcall(unsigned __int8 *, __int64, enum tagHTTP2ClientOpenedPacketType *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012110`

## callees

- `0x18001c1c0`
- `0x18001c91c`
- `0x18001c99c`
- `0x18001ca64`

## pseudocode

```c
__int64 __fastcall GetClientOpenedPacketType(unsigned __int8 *a1, __int64 a2, enum tagHTTP2ClientOpenedPacketType *a3)
{
  __int16 v4; // r9
  unsigned __int8 *v5; // rax
  __int16 v6; // r9
  unsigned __int8 *v7; // rcx
  _DWORD *v8; // r8
  unsigned int v9; // r10d
  int v10; // eax
  int v11; // r11d
  int v12; // ecx
  _DWORD *v13; // r8

  if ( (unsigned int)a2 < 0x14 )
    return 1728;
  v4 = *((_WORD *)a1 + 8);
  if ( (v4 & 4) != 0 )
  {
    *(_DWORD *)a3 = 2;
  }
  else if ( (v4 & 0x10) != 0 )
  {
    *(_DWORD *)a3 = 3;
  }
  else if ( (v4 & 0x20) != 0 )
  {
    *(_DWORD *)a3 = 6;
  }
  else if ( (unsigned int)a2 >= 0x18
         && (v5 = ValidateRTSPacketCommon(a1, a2)) != 0
         && *((_WORD *)a1 + 9) == 1
         && !v6
         && *(_DWORD *)v5 == 10 )
  {
    *(_DWORD *)a3 = 5;
  }
  else if ( (unsigned int)ParseD5_A6(a1, a2, a3) )
  {
    v10 = ParseEmptyRTSWithDestination(v7, v9);
    v12 = v11;
    LOBYTE(v12) = v10 == 0;
    *v13 = v12;
  }
  else
  {
    *v8 = 4;
  }
  return 0;
}

```

## disassembly

```asm
0x18001c1c0  sub     rsp, 28h
0x18001c1c4  mov     r10d, edx
0x18001c1c7  cmp     edx, 14h
0x18001c1ca  jnb     short loc_18001C1D6
0x18001c1cc  mov     eax, 6C0h
0x18001c1d1  jmp     loc_18001C25D
0x18001c1d6  movzx   r9d, word ptr [rcx+10h]
0x18001c1db  test    r9b, 4
0x18001c1df  jz      short loc_18001C1EA
0x18001c1e1  mov     dword ptr [r8], 2
0x18001c1e8  jmp     short loc_18001C25B
0x18001c1ea  test    r9b, 10h
0x18001c1ee  jz      short loc_18001C1F9
0x18001c1f0  mov     dword ptr [r8], 3
0x18001c1f7  jmp     short loc_18001C25B
0x18001c1f9  test    r9b, 20h
0x18001c1fd  jz      short loc_18001C208
0x18001c1ff  mov     dword ptr [r8], 6
0x18001c206  jmp     short loc_18001C25B
0x18001c208  xor     r11d, r11d
0x18001c20b  cmp     r10d, 18h
0x18001c20f  jb      short loc_18001C236
0x18001c211  call    ?ValidateRTSPacketCommon@@YAPEAEPEAEK@Z; ValidateRTSPacketCommon(uchar *,ulong)
0x18001c216  test    rax, rax
0x18001c219  jz      short loc_18001C236
0x18001c21b  cmp     word ptr [rcx+12h], 1
0x18001c220  jnz     short loc_18001C236
0x18001c222  test    r9w, r9w
0x18001c226  jnz     short loc_18001C236
0x18001c228  cmp     dword ptr [rax], 0Ah
0x18001c22b  jnz     short loc_18001C236
0x18001c22d  mov     dword ptr [r8], 5
0x18001c234  jmp     short loc_18001C25B
0x18001c236  call    ?ParseD5_A6@@YAJPEAEKW4tagForwardDestinations@@@Z; ParseD5_A6(uchar *,ulong,tagForwardDestinations)
0x18001c23b  test    eax, eax
0x18001c23d  jnz     short loc_18001C248
0x18001c23f  mov     dword ptr [r8], 4
0x18001c246  jmp     short loc_18001C25B
0x18001c248  mov     edx, r10d
0x18001c24b  call    ?ParseEmptyRTSWithDestination@@YAJPEAEKW4tagForwardDestinations@@@Z; ParseEmptyRTSWithDestination(uchar *,ulong,tagForwardDestinations)
0x18001c250  mov     ecx, r11d
0x18001c253  test    eax, eax
0x18001c255  setz    cl
0x18001c258  mov     [r8], ecx
0x18001c25b  xor     eax, eax
0x18001c25d  add     rsp, 28h
0x18001c261  retn
```
