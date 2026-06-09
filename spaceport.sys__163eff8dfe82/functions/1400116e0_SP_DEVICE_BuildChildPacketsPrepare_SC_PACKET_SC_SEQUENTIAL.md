# SP_DEVICE::BuildChildPacketsPrepare(SC_PACKET *,SC_SEQUENTIAL *)

- ea: `0x1400116e0`
- end: `0x140011960`
- name: `?BuildChildPacketsPrepare@SP_DEVICE@@AEAAJPEAVSC_PACKET@@PEAVSC_SEQUENTIAL@@@Z`
- size: `640`
- prototype: `__int64 __fastcall(SP_DEVICE *__hidden this, struct SC_PACKET *, struct SC_SEQUENTIAL *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140011410`
- `0x140011440`
- `0x140011570`

## callees

- `0x1400057f0`
- `0x140009f80`
- `0x1400116e0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001173e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001173e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140011717`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140011717`
- `HAL!KeQueryPerformanceCounter` at `0x1400117cb`
- `HAL!KeQueryPerformanceCounter` at `0x1400117cb`

## pseudocode

```c
__int64 __fastcall SP_DEVICE::BuildChildPacketsPrepare(SP_DEVICE *this, struct SC_PACKET *a2, SC_PACKET **a3)
{
  unsigned __int8 *v3; // rdi
  unsigned int v6; // ebx
  ULONG CurrentProcessorNumber; // eax
  unsigned __int64 v8; // rcx
  int v9; // ebx
  _WORD *v10; // rax
  SC_PACKET *v11; // rax
  SC_PACKET *v12; // rbx
  SC_PACKET *v13; // rax
  int v15; // eax
  unsigned __int8 v16; // dl
  _DWORD *v17; // rcx
  int v18; // ecx
  __int64 v19; // rax

  v3 = (unsigned __int8 *)*((_QWORD *)a2 + 23);
  if ( a3 )
  {
    v12 = *a3;
  }
  else
  {
    if ( *((_BYTE *)WPP_MAIN_CB.DeviceExtension + 435) )
      goto LABEL_6;
    v6 = *((_DWORD *)WPP_MAIN_CB.DeviceExtension + 84);
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    v8 = (unsigned __int64)(unsigned __int8)(CurrentProcessorNumber % v6) << 7;
    v9 = CurrentProcessorNumber % v6;
    v10 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 44) + v8));
    if ( !v10 )
      goto LABEL_6;
    v10[86] = 262;
    *((_BYTE *)v10 + 171) = v9;
    v11 = SC_PACKET::SC_PACKET((SC_PACKET *)v10);
    v12 = v11;
    if ( v11 )
    {
      *((_WORD *)v11 + 86) = 262;
    }
    else
    {
LABEL_6:
      v13 = (SC_PACKET *)SC_PACKET::operator new(0xF8u);
      if ( !v13 )
        return 3221225626LL;
      v12 = SC_PACKET::SC_PACKET(v13);
      if ( !v12 )
        return 3221225626LL;
    }
  }
  *((_DWORD *)v12 + 19) |= 4u;
  *((_QWORD *)v12 + 10) = a2;
  *((_DWORD *)v12 + 28) = 1;
  *((_QWORD *)v12 + 15) = *((_QWORD *)a2 + 1);
  *((LARGE_INTEGER *)v12 + 16) = KeQueryPerformanceCounter(0);
  *((_QWORD *)v12 + 17) = *((_QWORD *)v3 + 3);
  *((_DWORD *)v12 + 36) = *((_DWORD *)v3 + 2);
  *((_DWORD *)v12 + 41) = 0;
  v15 = *v3;
  *((_BYTE *)v12 + 168) = v15;
  *((_BYTE *)v12 + 170) = 1;
  switch ( v15 )
  {
    case 3:
      v17 = v3 + 16;
      if ( (v3[2] & 1) != 0 )
      {
        if ( (*v17 & 0xFFFFFE00) == 0x52434E00 )
        {
          *((_DWORD *)v12 + 38) = (unsigned __int8)*v17;
          if ( (*v17 & 0x100) != 0 )
            *((_BYTE *)v12 + 170) = 5;
        }
        if ( (v3[2] & 1) != 0 && *v17 == 71722322 )
          *((_DWORD *)v12 + 19) |= 0x20000u;
      }
      v18 = *((_DWORD *)WPP_MAIN_CB.DeviceExtension + 122);
      if ( v18 != -1 )
        *((_DWORD *)v12 + 38) = v18;
      goto LABEL_37;
    case 4:
      if ( *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 403) + 1160LL) + 70LL) )
      {
        if ( (v3[2] & 1) != 0 && *((_DWORD *)v3 + 4) == 54945106 )
          *((_DWORD *)v12 + 19) |= 0x400000u;
        else
          *((_DWORD *)v12 + 19) |= 0x800000u;
      }
      if ( v3[1] == 85 )
        *((_DWORD *)v12 + 19) |= 0x40000u;
      if ( (*((_DWORD *)a2 + 34) & 1) != 0 )
        *((_DWORD *)v12 + 19) |= 0x180000u;
      v16 = v3[2];
      if ( (v16 & 4) != 0 )
      {
        if ( *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 403) + 1160LL) + 66LL) )
          v3[2] = v16 & 0xFB;
        if ( !*((_BYTE *)WPP_MAIN_CB.DeviceExtension + 444) )
        {
          *((_DWORD *)v12 + 19) |= 0x200000u;
          _InterlockedIncrement((volatile signed __int32 *)this + 826);
        }
      }
      goto LABEL_37;
    case 9:
      *((_DWORD *)v12 + 19) |= 0x4000000u;
LABEL_37:
      v19 = *((_QWORD *)this + 17);
      if ( !v19 )
        v19 = *((_QWORD *)this + 403);
      *((_QWORD *)v12 + 30) = v19;
      *((_QWORD *)a2 + 15) = 1833528662;
      *((_QWORD *)a2 + 16) = v12;
      break;
  }
  return 0;
}

```

## disassembly

```asm
0x1400116e0  push    rbx
0x1400116e2  push    rbp
0x1400116e3  push    rsi
0x1400116e4  push    rdi
0x1400116e5  sub     rsp, 28h
0x1400116e9  mov     rdi, [rdx+0B8h]
0x1400116f0  mov     rbp, rdx
0x1400116f3  mov     rsi, rcx
0x1400116f6  test    r8, r8
0x1400116f9  jnz     loc_1400117A7
0x1400116ff  mov     rbx, cs:WPP_MAIN_CB.DeviceExtension
0x140011706  cmp     [rbx+1B3h], r8b
0x14001170d  jnz     short loc_140011779
0x14001170f  mov     ebx, [rbx+150h]
0x140011715  xor     ecx, ecx; ProcNumber
0x140011717  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14001171e  nop     dword ptr [rax+rax+00h]
0x140011723  xor     edx, edx
0x140011725  div     ebx
0x140011727  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14001172e  movzx   ecx, dl
0x140011731  shl     rcx, 7
0x140011735  mov     ebx, edx
0x140011737  add     rcx, [rax+160h]; Lookaside
0x14001173e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140011745  nop     dword ptr [rax+rax+00h]
0x14001174a  test    rax, rax
0x14001174d  jz      short loc_140011779
0x14001174f  mov     rcx, rax; this
0x140011752  mov     word ptr [rax+0ACh], 106h
0x14001175b  mov     [rax+0ABh], bl
0x140011761  call    ??0SC_PACKET@@QEAA@XZ; SC_PACKET::SC_PACKET(void)
0x140011766  mov     rbx, rax
0x140011769  test    rax, rax
0x14001176c  jz      short loc_140011779
0x14001176e  mov     word ptr [rax+0ACh], 106h
0x140011777  jmp     short loc_1400117AA
0x140011779  mov     ecx, 0F8h; NumberOfBytes
0x14001177e  call    ??2SC_PACKET@@SAPEAX_K@Z; SC_PACKET::operator new(unsigned __int64)
0x140011783  test    rax, rax
0x140011786  jz      short loc_140011798
0x140011788  mov     rcx, rax; this
0x14001178b  call    ??0SC_PACKET@@QEAA@XZ; SC_PACKET::SC_PACKET(void)
0x140011790  mov     rbx, rax
0x140011793  test    rax, rax
0x140011796  jnz     short loc_1400117AA
0x140011798  mov     eax, 0C000009Ah
0x14001179d  add     rsp, 28h
0x1400117a1  pop     rdi
0x1400117a2  pop     rsi
0x1400117a3  pop     rbp
0x1400117a4  pop     rbx
0x1400117a5  retn
0x1400117a7  mov     rbx, [r8]
0x1400117aa  or      dword ptr [rbx+4Ch], 4
0x1400117ae  xor     ecx, ecx; PerformanceFrequency
0x1400117b0  mov     [rbx+50h], rbp
0x1400117b4  mov     dword ptr [rbx+70h], 1
0x1400117bb  mov     rax, [rbp+8]
0x1400117bf  mov     [rsp+48h+arg_0], r14
0x1400117c4  xor     r14d, r14d
0x1400117c7  mov     [rbx+78h], rax
0x1400117cb  call    cs:__imp_KeQueryPerformanceCounter
0x1400117d2  nop     dword ptr [rax+rax+00h]
0x1400117d7  mov     [rbx+80h], rax
0x1400117de  mov     rax, [rdi+18h]
0x1400117e2  mov     [rbx+88h], rax
0x1400117e9  mov     eax, [rdi+8]
0x1400117ec  mov     [rbx+90h], eax
0x1400117f2  mov     [rbx+0A4h], r14d
0x1400117f9  movzx   eax, byte ptr [rdi]
0x1400117fc  mov     ecx, eax
0x1400117fe  mov     [rbx+0A8h], al
0x140011804  mov     byte ptr [rbx+0AAh], 1
0x14001180b  sub     ecx, 3
0x14001180e  jz      loc_1400118C6
0x140011814  sub     ecx, 1
0x140011817  jz      short loc_14001182E
0x140011819  cmp     ecx, 5
0x14001181c  jnz     loc_14001194E
0x140011822  or      dword ptr [rbx+4Ch], 4000000h
0x140011829  jmp     loc_140011925
0x14001182e  mov     rax, [rsi+0C98h]
0x140011835  mov     rcx, [rax+488h]
0x14001183c  cmp     [rcx+46h], r14b
0x140011840  jz      short loc_140011861
0x140011842  test    byte ptr [rdi+2], 1
0x140011846  jz      short loc_14001185A
0x140011848  cmp     dword ptr [rdi+10h], 3466552h
0x14001184f  jnz     short loc_14001185A
0x140011851  or      dword ptr [rbx+4Ch], 400000h
0x140011858  jmp     short loc_140011861
0x14001185a  or      dword ptr [rbx+4Ch], 800000h
0x140011861  cmp     byte ptr [rdi+1], 55h ; 'U'
0x140011865  jnz     short loc_14001186E
0x140011867  or      dword ptr [rbx+4Ch], 40000h
0x14001186e  mov     eax, [rbp+88h]
0x140011874  test    al, 1
0x140011876  jz      short loc_14001187F
0x140011878  or      dword ptr [rbx+4Ch], 180000h
0x14001187f  movzx   edx, byte ptr [rdi+2]
0x140011883  test    dl, 4
0x140011886  jz      loc_140011925
0x14001188c  mov     rax, [rsi+0C98h]
0x140011893  mov     rcx, [rax+488h]
0x14001189a  cmp     [rcx+42h], r14b
0x14001189e  jz      short loc_1400118A6
0x1400118a0  and     dl, 0FBh
0x1400118a3  mov     [rdi+2], dl
0x1400118a6  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x1400118ad  cmp     [rax+1BCh], r14b
0x1400118b4  jnz     short loc_140011925
0x1400118b6  or      dword ptr [rbx+4Ch], 200000h
0x1400118bd  lock inc dword ptr [rsi+0CE8h]
0x1400118c4  jmp     short loc_140011925
0x1400118c6  test    byte ptr [rdi+2], 1
0x1400118ca  lea     rcx, [rdi+10h]
0x1400118ce  jz      short loc_14001190D
0x1400118d0  mov     edx, [rcx]
0x1400118d2  mov     eax, edx
0x1400118d4  and     eax, 0FFFFFE00h
0x1400118d9  cmp     eax, 52434E00h
0x1400118de  jnz     short loc_1400118F8
0x1400118e0  movzx   eax, dl
0x1400118e3  mov     [rbx+98h], eax
0x1400118e9  test    dword ptr [rcx], 100h
0x1400118ef  jz      short loc_1400118F8
0x1400118f1  mov     byte ptr [rbx+0AAh], 5
0x1400118f8  test    byte ptr [rdi+2], 1
0x1400118fc  jz      short loc_14001190D
0x1400118fe  cmp     dword ptr [rcx], 4466552h
0x140011904  jnz     short loc_14001190D
0x140011906  or      dword ptr [rbx+4Ch], 20000h
0x14001190d  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x140011914  mov     ecx, [rax+1E8h]
0x14001191a  cmp     ecx, 0FFFFFFFFh
0x14001191d  jz      short loc_140011925
0x14001191f  mov     [rbx+98h], ecx
0x140011925  mov     rax, [rsi+88h]
0x14001192c  test    rax, rax
0x14001192f  jnz     short loc_140011938
0x140011931  mov     rax, [rsi+0C98h]
0x140011938  mov     [rbx+0F0h], rax
0x14001193f  mov     qword ptr [rbp+78h], 6D496D56h
0x140011947  mov     [rbp+80h], rbx
0x14001194e  mov     eax, r14d
0x140011951  mov     r14, [rsp+48h+arg_0]
0x140011956  add     rsp, 28h
0x14001195a  pop     rdi
0x14001195b  pop     rsi
0x14001195c  pop     rbp
0x14001195d  pop     rbx
0x14001195e  retn
```
