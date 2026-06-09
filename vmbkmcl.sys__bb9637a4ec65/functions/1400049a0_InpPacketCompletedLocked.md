# InpPacketCompletedLocked

- ea: `0x1400049a0`
- end: `0x140004bdd`
- name: `InpPacketCompletedLocked`
- size: `573`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140004cc0`
- `0x1400089a8`

## callees

- `0x140001120`
- `0x140002170`
- `0x1400049a0`
- `0x140005cf0`
- `0x14000ad30`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140004b82`
- `ntoskrnl!KeSetEvent` at `0x140004b82`

## pseudocode

```c
int __fastcall InpPacketCompletedLocked(__int64 a1, char a2)
{
  int v2; // eax
  char v3; // r9
  __int64 v5; // rax
  int v6; // ecx
  int v7; // r8d
  int v8; // edx
  __int64 v9; // rax
  void *v10; // rcx
  struct _KEVENT *v11; // rcx

  v2 = *(_DWORD *)(a1 + 1096);
  v3 = 0;
  if ( a2 )
  {
    --*(_DWORD *)(a1 + 1160);
    if ( v2 == 4 )
    {
      if ( !(unsigned __int8)PkIsIncomingRingEmpty(a1 + 64) )
      {
        ++*(_DWORD *)(a1 + 1148);
        LODWORD(v5) = *(_DWORD *)(a1 + 1096);
        goto LABEL_4;
      }
      if ( *(_DWORD *)(a1 + 1160) + *(_DWORD *)(a1 + 1320) == *(_DWORD *)(a1 + 1324) - 1
        && !(unsigned __int8)InpDisableInterruptMaskingAndPollLocked(a1) )
      {
        v3 = 1;
      }
    }
  }
  else if ( v2 == 4 && *(_BYTE *)(a1 + 1200) && !(unsigned __int8)PkIsIncomingRingEmpty(a1 + 64) )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 88) + 8LL) = 1;
    *(_BYTE *)(a1 + 1100) |= 4u;
    ++*(_DWORD *)(a1 + 1148);
    LODWORD(v5) = *(_DWORD *)(a1 + 1096);
    goto LABEL_4;
  }
  ++*(_DWORD *)(a1 + 1148);
  LODWORD(v5) = *(_DWORD *)(a1 + 1096);
  if ( !v3 )
  {
    if ( (_DWORD)v5 == 2 )
    {
      LODWORD(v5) = InpPrepareToQueueWorkerLocked(a1, 0, 0);
      if ( (_BYTE)v5 )
        ++*(_DWORD *)(a1 + 1180);
    }
    else if ( (_DWORD)v5 == 9 && *(_DWORD *)(a1 + 1152) + *(_DWORD *)(a1 + 1148) == *(_DWORD *)(a1 + 1316) )
    {
      v10 = *(void **)a1;
      *(_DWORD *)(a1 + 1096) = 0;
      LODWORD(v5) = KmclDecrementRundownCount(v10);
    }
    return v5;
  }
LABEL_4:
  if ( (_DWORD)v5 == 1 && (v11 = *(struct _KEVENT **)(a1 + 1216)) != 0 )
  {
    KeSetEvent(v11, 0, 0);
    LODWORD(v5) = 0;
    *(_QWORD *)(a1 + 1216) = 0;
    *(_QWORD *)(a1 + 1128) = 0;
  }
  else
  {
    LODWORD(v5) = 0;
    *(_DWORD *)(a1 + 1096) = 2;
    *(_QWORD *)(a1 + 1128) = 0;
    if ( !*(_QWORD *)(a1 + 1136) )
    {
      LODWORD(v5) = HIDWORD(KeGetPcr()[1].LockArray);
      v6 = *(_DWORD *)(a1 + 1632);
      if ( v6 != (_DWORD)v5 )
      {
        v7 = *(_DWORD *)(a1 + 1636);
        if ( v7 != (_DWORD)v5 )
        {
          v8 = *(_DWORD *)(a1 + 1640);
          if ( v8 != (_DWORD)v5 )
          {
            if ( *(_BYTE *)(a1 + 1201) )
            {
              if ( v8 != -1 )
                return v5;
              *(_BYTE *)(a1 + 1100) |= 2u;
              ++*(_QWORD *)(a1 + 1184);
              *(_DWORD *)(a1 + 1640) = v5;
              v5 = *(_QWORD *)(a1 + 1624);
            }
            else
            {
              if ( v6 == -1 )
              {
                *(_DWORD *)(a1 + 1632) = v5;
                v9 = 1496;
              }
              else
              {
                if ( v7 != -1 )
                  return v5;
                *(_DWORD *)(a1 + 1636) = v5;
                v9 = 1560;
              }
              ++*(_QWORD *)(a1 + 1192);
              v5 = a1 + v9;
              *(_BYTE *)(a1 + 1100) &= ~1u;
            }
            ++*(_DWORD *)(a1 + 1164);
            ++*(_DWORD *)(a1 + 1176);
            *(_QWORD *)(a1 + 1136) = v5;
          }
        }
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1400049a0  push    rbx
0x1400049a2  sub     rsp, 20h
0x1400049a6  mov     eax, [rcx+448h]
0x1400049ac  xor     r9b, r9b
0x1400049af  mov     rbx, rcx
0x1400049b2  test    dl, dl
0x1400049b4  jnz     loc_140004ACB
0x1400049ba  cmp     eax, 4
0x1400049bd  jz      loc_140004B2C
0x1400049c3  inc     dword ptr [rbx+47Ch]
0x1400049c9  mov     ecx, [rbx+47Ch]
0x1400049cf  mov     eax, [rbx+448h]
0x1400049d5  test    r9b, r9b
0x1400049d8  jz      loc_140004A73
0x1400049de  cmp     eax, 1
0x1400049e1  jz      loc_140004B6D
0x1400049e7  xor     eax, eax
0x1400049e9  mov     dword ptr [rbx+448h], 2
0x1400049f3  mov     [rbx+468h], rax
0x1400049fa  cmp     [rbx+470h], rax
0x140004a01  jnz     short loc_140004A6C
0x140004a03  mov     eax, gs:1A4h
0x140004a0b  mov     ecx, [rbx+660h]
0x140004a11  cmp     ecx, eax
0x140004a13  jz      short loc_140004A6C
0x140004a15  mov     r8d, [rbx+664h]
0x140004a1c  cmp     r8d, eax
0x140004a1f  jz      short loc_140004A6C
0x140004a21  mov     edx, [rbx+668h]
0x140004a27  cmp     edx, eax
0x140004a29  jz      short loc_140004A6C
0x140004a2b  cmp     byte ptr [rbx+4B1h], 0
0x140004a32  jnz     short loc_140004AA9
0x140004a34  cmp     ecx, 0FFFFFFFFh
0x140004a37  jnz     loc_140004BA3
0x140004a3d  mov     [rbx+660h], eax
0x140004a43  mov     eax, 5D8h
0x140004a48  inc     qword ptr [rbx+4A8h]
0x140004a4f  add     rax, rbx
0x140004a52  and     byte ptr [rbx+44Ch], 0FEh
0x140004a59  inc     dword ptr [rbx+48Ch]
0x140004a5f  inc     dword ptr [rbx+498h]
0x140004a65  mov     [rbx+470h], rax
0x140004a6c  add     rsp, 20h
0x140004a70  pop     rbx
0x140004a71  retn
0x140004a73  cmp     eax, 2
0x140004a76  jz      loc_140004BBD
0x140004a7c  cmp     eax, 9
0x140004a7f  jnz     short loc_140004A6C
0x140004a81  add     ecx, [rbx+480h]
0x140004a87  cmp     ecx, [rbx+524h]
0x140004a8d  jnz     short loc_140004A6C
0x140004a8f  mov     rcx, [rbx]; Context
0x140004a92  xor     eax, eax
0x140004a94  mov     r8d, 8E6h
0x140004a9a  mov     [rbx+448h], eax
0x140004aa0  mov     dl, 1
0x140004aa2  call    KmclDecrementRundownCount
0x140004aa7  jmp     short loc_140004A6C
0x140004aa9  cmp     edx, 0FFFFFFFFh
0x140004aac  jnz     short loc_140004A6C
0x140004aae  or      byte ptr [rbx+44Ch], 2
0x140004ab5  inc     qword ptr [rbx+4A0h]
0x140004abc  mov     [rbx+668h], eax
0x140004ac2  mov     rax, [rbx+658h]
0x140004ac9  jmp     short loc_140004A59
0x140004acb  dec     dword ptr [rcx+488h]
0x140004ad1  cmp     eax, 4
0x140004ad4  jnz     loc_1400049C3
0x140004ada  add     rcx, 40h ; '@'
0x140004ade  call    PkIsIncomingRingEmpty
0x140004ae3  test    al, al
0x140004ae5  jnz     short loc_140004AF8
0x140004ae7  inc     dword ptr [rbx+47Ch]
0x140004aed  mov     eax, [rbx+448h]
0x140004af3  jmp     loc_1400049DE
0x140004af8  mov     ecx, [rbx+528h]
0x140004afe  mov     eax, [rbx+52Ch]
0x140004b04  add     ecx, [rbx+488h]
0x140004b0a  dec     eax
0x140004b0c  cmp     ecx, eax
0x140004b0e  jnz     loc_1400049C3
0x140004b14  mov     rcx, rbx
0x140004b17  call    InpDisableInterruptMaskingAndPollLocked
0x140004b1c  test    al, al
0x140004b1e  jnz     loc_1400049C3
0x140004b24  mov     r9b, 1
0x140004b27  jmp     loc_1400049C3
0x140004b2c  cmp     [rcx+4B0h], r9b
0x140004b33  jz      loc_1400049C3
0x140004b39  add     rcx, 40h ; '@'
0x140004b3d  call    PkIsIncomingRingEmpty
0x140004b42  test    al, al
0x140004b44  jnz     loc_1400049C3
0x140004b4a  mov     rax, [rbx+58h]
0x140004b4e  mov     dword ptr [rax+8], 1
0x140004b55  or      byte ptr [rbx+44Ch], 4
0x140004b5c  inc     dword ptr [rbx+47Ch]
0x140004b62  mov     eax, [rbx+448h]
0x140004b68  jmp     loc_1400049DE
0x140004b6d  mov     rcx, [rbx+4C0h]; Event
0x140004b74  test    rcx, rcx
0x140004b77  jz      loc_1400049E7
0x140004b7d  xor     r8d, r8d; Wait
0x140004b80  xor     edx, edx; Increment
0x140004b82  call    cs:__imp_KeSetEvent
0x140004b89  nop     dword ptr [rax+rax+00h]
0x140004b8e  xor     eax, eax
0x140004b90  mov     [rbx+4C0h], rax
0x140004b97  mov     [rbx+468h], rax
0x140004b9e  jmp     loc_140004A6C
0x140004ba3  cmp     r8d, 0FFFFFFFFh
0x140004ba7  jnz     loc_140004A6C
0x140004bad  mov     [rbx+664h], eax
0x140004bb3  mov     eax, 618h
0x140004bb8  jmp     loc_140004A48
0x140004bbd  xor     r8d, r8d
0x140004bc0  xor     edx, edx
0x140004bc2  mov     rcx, rbx
0x140004bc5  call    InpPrepareToQueueWorkerLocked
0x140004bca  test    al, al
0x140004bcc  jz      loc_140004A6C
0x140004bd2  inc     dword ptr [rbx+49Ch]
0x140004bd8  jmp     loc_140004A6C
```
