# TpmTransportType::CreateTpmTransport(WDFDEVICE__ *,int,TpmTransport * *)

- ea: `0x14001a0f4`
- end: `0x14001a2d9`
- name: `?CreateTpmTransport@TpmTransportType@@SAJPEAUWDFDEVICE__@@HPEAPEAVTpmTransport@@@Z`
- size: `485`
- prototype: `__int64 __fastcall(struct WDFDEVICE__ *, int, struct TpmTransport **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001483c`

## callees

- `0x1400104b4`
- `0x14001a0f4`
- `0x140022ba0`
- `0x140022cd8`
- `0x140022ea0`
- `0x140024e50`
- `0x140028458`
- `0x140028568`

## pseudocode

```c
__int64 __fastcall TpmTransportType::CreateTpmTransport(struct WDFDEVICE__ *a1, int a2, struct TpmTransport **a3)
{
  TpmTransportCommandResponse *v7; // rax
  TpmTransportTis *v8; // rbx
  TpmTransport *v9; // rax
  TpmTransportCommandResponse *v10; // rax
  int v11; // r9d
  TpmTransportTis *v12; // rax
  TpmTransportTis *v13; // rax
  TpmTransportTis *v14; // rax
  int v15; // edi

  switch ( LODWORD(WPP_MAIN_CB.DeviceExtension) )
  {
    case 1:
      goto LABEL_21;
    case 4:
      v13 = (TpmTransportTis *)AllocatorBaseNonPaged::operator new(0x210u);
      v8 = v13;
      if ( v13 )
      {
        TpmTransportMemBase::TpmTransportMemBase(v13, a1, a2);
        *((_QWORD *)v8 + 65) = 0;
        *(_QWORD *)v8 = &TpmTransportACPI::`vftable';
        *((_DWORD *)v8 + 2) = TpmTransportACPI::InitACPIWorkitem(v8);
        goto LABEL_25;
      }
      goto LABEL_20;
    case 6:
LABEL_21:
      v14 = (TpmTransportTis *)AllocatorBaseNonPaged::operator new(0x170u);
      if ( !v14 )
        return 3221225626LL;
      v12 = TpmTransportTis::TpmTransportTis(v14, a1, a2);
      goto LABEL_23;
    case 7:
      v10 = (TpmTransportCommandResponse *)AllocatorBaseNonPaged::operator new(0x218u);
      if ( !v10 )
        goto LABEL_20;
      v11 = 0;
LABEL_15:
      v12 = TpmTransportCommandResponse::TpmTransportCommandResponse(v10, a1, a2, v11);
LABEL_23:
      v8 = v12;
LABEL_24:
      if ( v8 )
        goto LABEL_25;
      return 3221225626LL;
    case 8:
      v10 = (TpmTransportCommandResponse *)AllocatorBaseNonPaged::operator new(0x218u);
      if ( !v10 )
        goto LABEL_20;
      v11 = 1;
      goto LABEL_15;
    case 0xA:
      v9 = (TpmTransport *)AllocatorBaseNonPaged::operator new(0x158u);
      v8 = v9;
      if ( v9 )
      {
        TpmTransport::TpmTransport(v9, a1, a2);
        *((_DWORD *)v8 + 78) = -1;
        *(_QWORD *)v8 = &TpmTransportSpb::`vftable';
        *((_DWORD *)v8 + 2) = 0;
        *(_QWORD *)((char *)v8 + 316) = 0;
        *((_QWORD *)v8 + 42) = 0;
        goto LABEL_25;
      }
      goto LABEL_20;
  }
  if ( LODWORD(WPP_MAIN_CB.DeviceExtension) != 13 )
    return 3221225473LL;
  v7 = (TpmTransportCommandResponse *)AllocatorBaseNonPaged::operator new(0x230u);
  v8 = v7;
  if ( !v7 )
  {
LABEL_20:
    v8 = 0;
    goto LABEL_24;
  }
  TpmTransportCommandResponse::TpmTransportCommandResponse(v7, a1, a2, 0);
  *((_QWORD *)v8 + 67) = 0;
  *(_QWORD *)v8 = &TpmTransportCommandResponseHsp::`vftable';
  *((_QWORD *)v8 + 68) = 0;
  *((_QWORD *)v8 + 69) = 0;
  *((_DWORD *)v8 + 2) = 0;
LABEL_25:
  v15 = *((_DWORD *)v8 + 2);
  if ( v15 >= 0 )
    *a3 = v8;
  else
    TpmTransport::DeleteTpmTransport(v8);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14001a0f4  push    rbx
0x14001a0f6  push    rsi
0x14001a0f7  push    rdi
0x14001a0f8  push    r14
0x14001a0fa  sub     rsp, 28h
0x14001a0fe  mov     r9d, dword ptr cs:WPP_MAIN_CB.DeviceExtension
0x14001a105  mov     r14, r8
0x14001a108  mov     edi, edx
0x14001a10a  mov     rsi, rcx
0x14001a10d  sub     r9d, 1
0x14001a111  jz      loc_14001A28C
0x14001a117  sub     r9d, 3
0x14001a11b  jz      loc_14001A246
0x14001a121  sub     r9d, 2
0x14001a125  jz      loc_14001A28C
0x14001a12b  sub     r9d, 1
0x14001a12f  jz      loc_14001A232
0x14001a135  sub     r9d, 1
0x14001a139  jz      loc_14001A20D
0x14001a13f  sub     r9d, 2
0x14001a143  jz      short loc_14001A1B3
0x14001a145  cmp     r9d, 3
0x14001a149  jz      short loc_14001A155
0x14001a14b  mov     eax, 0C0000001h
0x14001a150  jmp     loc_14001A2CE
0x14001a155  mov     ecx, 230h; Size
0x14001a15a  call    ??2AllocatorBaseNonPaged@@SAPEAX_K@Z; AllocatorBaseNonPaged::operator new(unsigned __int64)
0x14001a15f  mov     rbx, rax
0x14001a162  test    rax, rax
0x14001a165  jz      loc_14001A288
0x14001a16b  xor     r9d, r9d; int
0x14001a16e  mov     r8d, edi; int
0x14001a171  mov     rdx, rsi; struct WDFDEVICE__ *
0x14001a174  mov     rcx, rax; this
0x14001a177  call    ??0TpmTransportCommandResponse@@QEAA@PEAUWDFDEVICE__@@HH@Z; TpmTransportCommandResponse::TpmTransportCommandResponse(WDFDEVICE__ *,int,int)
0x14001a17c  lea     rax, ??_7TpmTransportCommandResponseHsp@@6B@; const TpmTransportCommandResponseHsp::`vftable'
0x14001a183  mov     qword ptr [rbx+218h], 0
0x14001a18e  mov     [rbx], rax
0x14001a191  mov     qword ptr [rbx+220h], 0
0x14001a19c  mov     qword ptr [rbx+228h], 0
0x14001a1a7  mov     dword ptr [rbx+8], 0
0x14001a1ae  jmp     loc_14001A2B1
0x14001a1b3  mov     ecx, 158h; Size
0x14001a1b8  call    ??2AllocatorBaseNonPaged@@SAPEAX_K@Z; AllocatorBaseNonPaged::operator new(unsigned __int64)
0x14001a1bd  mov     rbx, rax
0x14001a1c0  test    rax, rax
0x14001a1c3  jz      loc_14001A288
0x14001a1c9  mov     r8d, edi; int
0x14001a1cc  mov     rdx, rsi; struct WDFDEVICE__ *
0x14001a1cf  mov     rcx, rax; this
0x14001a1d2  call    ??0TpmTransport@@IEAA@PEAUWDFDEVICE__@@H@Z; TpmTransport::TpmTransport(WDFDEVICE__ *,int)
0x14001a1d7  lea     rax, ??_7TpmTransportSpb@@6B@; const TpmTransportSpb::`vftable'
0x14001a1de  mov     dword ptr [rbx+138h], 0FFFFFFFFh
0x14001a1e8  mov     [rbx], rax
0x14001a1eb  mov     dword ptr [rbx+8], 0
0x14001a1f2  mov     qword ptr [rbx+13Ch], 0
0x14001a1fd  mov     qword ptr [rbx+150h], 0
0x14001a208  jmp     loc_14001A2B1
0x14001a20d  mov     ecx, 218h; Size
0x14001a212  call    ??2AllocatorBaseNonPaged@@SAPEAX_K@Z; AllocatorBaseNonPaged::operator new(unsigned __int64)
0x14001a217  test    rax, rax
0x14001a21a  jz      short loc_14001A288
0x14001a21c  mov     r9d, 1; int
0x14001a222  mov     r8d, edi; int
0x14001a225  mov     rdx, rsi; struct WDFDEVICE__ *
0x14001a228  mov     rcx, rax; this
0x14001a22b  call    ??0TpmTransportCommandResponse@@QEAA@PEAUWDFDEVICE__@@HH@Z; TpmTransportCommandResponse::TpmTransportCommandResponse(WDFDEVICE__ *,int,int)
0x14001a230  jmp     short loc_14001A2A9
0x14001a232  mov     ecx, 218h; Size
0x14001a237  call    ??2AllocatorBaseNonPaged@@SAPEAX_K@Z; AllocatorBaseNonPaged::operator new(unsigned __int64)
0x14001a23c  test    rax, rax
0x14001a23f  jz      short loc_14001A288
0x14001a241  xor     r9d, r9d
0x14001a244  jmp     short loc_14001A222
0x14001a246  mov     ecx, 210h; Size
0x14001a24b  call    ??2AllocatorBaseNonPaged@@SAPEAX_K@Z; AllocatorBaseNonPaged::operator new(unsigned __int64)
0x14001a250  mov     rbx, rax
0x14001a253  test    rax, rax
0x14001a256  jz      short loc_14001A288
0x14001a258  mov     r8d, edi; int
0x14001a25b  mov     rdx, rsi; struct WDFDEVICE__ *
0x14001a25e  mov     rcx, rax; Context
0x14001a261  call    ??0TpmTransportMemBase@@QEAA@PEAUWDFDEVICE__@@H@Z; TpmTransportMemBase::TpmTransportMemBase(WDFDEVICE__ *,int)
0x14001a266  lea     rax, ??_7TpmTransportACPI@@6B@; const TpmTransportACPI::`vftable'
0x14001a26d  mov     qword ptr [rbx+208h], 0
0x14001a278  mov     rcx, rbx; this
0x14001a27b  mov     [rbx], rax
0x14001a27e  call    ?InitACPIWorkitem@TpmTransportACPI@@AEAAJXZ; TpmTransportACPI::InitACPIWorkitem(void)
0x14001a283  mov     [rbx+8], eax
0x14001a286  jmp     short loc_14001A2B1
0x14001a288  xor     ebx, ebx
0x14001a28a  jmp     short loc_14001A2AC
0x14001a28c  mov     ecx, 170h; Size
0x14001a291  call    ??2AllocatorBaseNonPaged@@SAPEAX_K@Z; AllocatorBaseNonPaged::operator new(unsigned __int64)
0x14001a296  test    rax, rax
0x14001a299  jz      short loc_14001A2C9
0x14001a29b  mov     r8d, edi; int
0x14001a29e  mov     rdx, rsi; struct WDFDEVICE__ *
0x14001a2a1  mov     rcx, rax; this
0x14001a2a4  call    ??0TpmTransportTis@@QEAA@PEAUWDFDEVICE__@@H@Z; TpmTransportTis::TpmTransportTis(WDFDEVICE__ *,int)
0x14001a2a9  mov     rbx, rax
0x14001a2ac  test    rbx, rbx
0x14001a2af  jz      short loc_14001A2C9
0x14001a2b1  mov     edi, [rbx+8]
0x14001a2b4  test    edi, edi
0x14001a2b6  jns     short loc_14001A2C2
0x14001a2b8  mov     rcx, rbx; struct TpmTransport *
0x14001a2bb  call    ?DeleteTpmTransport@TpmTransport@@SAXPEAV1@@Z; TpmTransport::DeleteTpmTransport(TpmTransport *)
0x14001a2c0  jmp     short loc_14001A2C5
0x14001a2c2  mov     [r14], rbx
0x14001a2c5  mov     eax, edi
0x14001a2c7  jmp     short loc_14001A2CE
0x14001a2c9  mov     eax, 0C000009Ah
0x14001a2ce  add     rsp, 28h
0x14001a2d2  pop     r14
0x14001a2d4  pop     rdi
0x14001a2d5  pop     rsi
0x14001a2d6  pop     rbx
0x14001a2d7  retn
```
