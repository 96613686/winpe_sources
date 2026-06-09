# FileProvReadCompressedOnNewStackExtendedCompletion

- ea: `0x140001890`
- end: `0x140001c94`
- name: `FileProvReadCompressedOnNewStackExtendedCompletion`
- size: `1028`
- prototype: `__int64 __fastcall(_QWORD *Entry)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140001890`
- `0x140001ca0`
- `0x1400022a0`
- `0x14000d3b8`
- `0x14000fb60`
- `0x140011640`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140001bae`
- `ntoskrnl!KeSetEvent` at `0x140001bae`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001bcc`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001bcc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001991`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001991`
- `ntoskrnl!KeInitializeEvent` at `0x14000196e`
- `ntoskrnl!KeInitializeEvent` at `0x14000196e`

## pseudocode

```c
__int64 __fastcall FileProvReadCompressedOnNewStackExtendedCompletion(_QWORD *Entry)
{
  __int64 v1; // rbx
  __int64 v2; // rdi
  _BYTE *v3; // r13
  unsigned int v4; // r15d
  __int64 v5; // rax
  __int64 v6; // rsi
  __int64 *v7; // r12
  unsigned int v8; // ebp
  _QWORD *v9; // rax
  _QWORD *v10; // rsi
  __int64 v11; // r11
  unsigned int v12; // ecx
  __int64 v13; // rdx
  __int64 v14; // r8
  int v15; // r9d
  int v16; // r10d
  unsigned int v17; // r12d
  unsigned int v18; // edx
  __int64 v19; // r11
  unsigned int v20; // r12d
  __int64 v21; // rcx
  unsigned int v22; // edx
  __int64 v23; // r13
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 v26; // rcx
  int v27; // r10d
  __int64 v28; // rdx
  unsigned int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rcx
  unsigned int v32; // ebx
  __int64 result; // rax
  __int64 v34; // [rsp+30h] [rbp-88h]
  __int64 *v35; // [rsp+38h] [rbp-80h]
  _QWORD Event[4]; // [rsp+40h] [rbp-78h] BYREF
  __int64 v37; // [rsp+60h] [rbp-58h]
  unsigned int v39; // [rsp+C8h] [rbp+10h]
  __int64 v40; // [rsp+D0h] [rbp+18h]
  __int64 v41; // [rsp+D8h] [rbp+20h]

  v1 = Entry[6];
  v2 = Entry[23];
  v3 = Entry;
  v4 = *((_DWORD *)Entry + 18);
  LODWORD(v37) = 0;
  v40 = Entry[24];
  v39 = *((_DWORD *)Entry + 50);
  v34 = Entry[10];
  v5 = Entry[7];
  memset(Event, 0, sizeof(Event));
  v41 = v5;
  v6 = *(unsigned int *)(v5 + 4);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
  if ( *((int *)v3 + 2) < 0 )
  {
    v32 = 0;
  }
  else
  {
    v7 = &g_CompressionScheme[104 * v6];
    LODWORD(Event[0]) = 1;
    v35 = v7;
    v8 = 0;
    KeInitializeEvent((PRKEVENT)&Event[1], SynchronizationEvent, 0);
    v37 = 0;
    while ( v8 < v4 )
    {
      v9 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v7 + 4);
      v10 = v9;
      if ( !v9 )
      {
        LODWORD(v37) = -1073741670;
        break;
      }
      _InterlockedIncrement((volatile signed __int32 *)Event);
      v9[1] = 0;
      v9[2] = FileProvDecompressChunks;
      v9[3] = v9;
      *v9 = 0;
      v9[4] = v41;
      *((_BYTE *)v9 + 40) = v3[92];
      v9[6] = v8 + v34;
      v11 = v8 + v1;
      v9[8] = v11;
      v12 = *((_DWORD *)v7 + 1);
      *((_DWORD *)v9 + 18) = v12;
      v13 = v11 % *(unsigned int *)v7;
      if ( v13 <= 0 )
      {
        v14 = v12;
      }
      else
      {
        v14 = (unsigned int)(*(_DWORD *)v7 - v13);
        *((_DWORD *)v9 + 18) = v14;
      }
      if ( (unsigned int)v14 > v4 - v8 )
        *((_DWORD *)v9 + 18) = v4 - v8;
      *(_QWORD *)((char *)v9 + 76) = 0;
      v9[11] = Event;
      if ( v2 )
      {
        v15 = 0;
        v16 = 0;
        v17 = v11 / *(unsigned int *)v7;
        v18 = v17 / 0xD;
        v19 = 16LL * (v17 / 0xD);
        v20 = v17 % 0xD;
        v21 = 32LL * v18;
        v22 = 0;
        v23 = *(_QWORD *)(v21 + v2);
        if ( v20 >= 2 )
        {
          v24 = v19 + 4;
          do
          {
            v25 = v24 + v22;
            v26 = v24 + v22 + 1;
            v22 += 2;
            v15 += *(unsigned __int16 *)(v2 + 2 * v25);
            v16 += *(unsigned __int16 *)(v2 + 2 * v26);
          }
          while ( v22 < v20 - 1 );
        }
        if ( v22 < v20 )
          LODWORD(v23) = *(unsigned __int16 *)(v2 + 2 * (v19 + v22) + 8) + (_DWORD)v23;
        v27 = v23 + v15 + v16;
        v14 = v39 / 0xD;
        v28 = *(_QWORD *)(32 * v14 + v2);
        v29 = 0;
        if ( v39 % 0xD )
        {
          v14 = 16 * v14 + 4;
          do
          {
            v30 = v29++;
            LODWORD(v28) = *(unsigned __int16 *)(v2 + 2 * (v14 + v30)) + (_DWORD)v28;
          }
          while ( v29 < v39 % 0xD );
        }
        v3 = Entry;
        v7 = v35;
        v31 = (unsigned int)(v27 - v28) + v40;
      }
      else
      {
        v31 = v40;
      }
      v10[7] = v31;
      v8 += *((_DWORD *)v10 + 18);
      _InterlockedIncrement(&WimPostedReads);
      if ( v8 >= v4
        || !ExTryQueueWorkItemWrapper
        || !(unsigned __int8)ExTryQueueWorkItemWrapper(v10, (unsigned int)(*((_DWORD *)v3 + 24) + 32), v14) )
      {
        _InterlockedDecrement(&WimPostedReads);
        _InterlockedIncrement(&WimInlineReads);
        FileProvDecompressChunks(v10);
      }
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Event, 0xFFFFFFFF) == 1 )
      KeSetEvent((PRKEVENT)&Event[1], 0, 0);
    KeWaitForSingleObject(&Event[1], Executive, 0, 0, 0);
    v32 = v37;
  }
  FileProvCompleteRead(v3);
  result = HIDWORD(WPP_GLOBAL_Control->Timer);
  if ( (result & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    return WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_3b099794e4b93327e327da255c047df6_Traceguids, v32);
  return result;
}

```

## disassembly

```asm
0x140001890  mov     rax, rsp
0x140001893  mov     [rax+8], rcx
0x140001897  push    rbx
0x140001898  sub     rsp, 0B0h
0x14000189f  mov     rbx, [rcx+30h]
0x1400018a3  xorps   xmm0, xmm0
0x1400018a6  mov     [rax-18h], rsi
0x1400018aa  mov     [rax-20h], rdi
0x1400018ae  mov     rdi, [rcx+0B8h]
0x1400018b5  mov     [rax-30h], r13
0x1400018b9  mov     r13, rcx
0x1400018bc  mov     [rax-40h], r15
0x1400018c0  xor     eax, eax
0x1400018c2  mov     r15d, [rcx+48h]
0x1400018c6  mov     dword ptr [rsp+0B8h+var_58], eax
0x1400018ca  mov     rax, [rcx+0C0h]
0x1400018d1  mov     [rsp+0B8h+arg_10], rax
0x1400018d9  mov     eax, [rcx+0C8h]
0x1400018df  mov     [rsp+0B8h+arg_8], eax
0x1400018e6  mov     rax, [rcx+50h]
0x1400018ea  mov     [rsp+0B8h+var_88], rax
0x1400018ef  mov     rax, [rcx+38h]
0x1400018f3  movups  xmmword ptr [rsp+0B8h+Event], xmm0
0x1400018f8  mov     [rsp+0B8h+arg_18], rax
0x140001900  movups  xmmword ptr [rsp+0B8h+Event+10h], xmm0
0x140001905  mov     esi, [rax+4]
0x140001908  mov     rcx, cs:WPP_GLOBAL_Control
0x14000190f  mov     eax, [rcx+2Ch]
0x140001912  test    al, 20h
0x140001914  jnz     loc_140001C43
0x14000191a  cmp     dword ptr [r13+8], 0
0x14000191f  jl      loc_140001C3D
0x140001925  mov     [rsp+0B8h+var_10], rbp
0x14000192d  lea     rax, g_CompressionScheme
0x140001934  mov     [rsp+0B8h+var_28], r12
0x14000193c  lea     rcx, [rsp+0B8h+Event+8]; Event
0x140001941  imul    r12, rsi, 340h
0x140001948  mov     [rsp+0B8h+var_38], r14
0x140001950  xor     r8d, r8d; State
0x140001953  add     r12, rax
0x140001956  mov     dword ptr [rsp+0B8h+Event], 1
0x14000195e  xor     r14d, r14d
0x140001961  mov     [rsp+0B8h+var_80], r12
0x140001966  mov     edx, 1; Type
0x14000196b  mov     ebp, r14d
0x14000196e  call    cs:__imp_KeInitializeEvent
0x140001975  nop     dword ptr [rax+rax+00h]
0x14000197a  mov     [rsp+0B8h+var_58], r14
0x14000197f  nop
0x140001980  cmp     ebp, r15d
0x140001983  jnb     loc_140001B84
0x140001989  lea     rcx, [r12+200h]; Lookaside
0x140001991  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140001998  nop     dword ptr [rax+rax+00h]
0x14000199d  mov     rsi, rax
0x1400019a0  test    rax, rax
0x1400019a3  jz      loc_140001C67
0x1400019a9  lock inc dword ptr [rsp+0B8h+Event]
0x1400019ae  mov     [rax+8], r14
0x1400019b2  lea     rax, FileProvDecompressChunks
0x1400019b9  mov     [rsi+10h], rax
0x1400019bd  mov     rax, [rsp+0B8h+arg_18]
0x1400019c5  mov     [rsi+18h], rsi
0x1400019c9  mov     [rsi], r14
0x1400019cc  mov     [rsi+20h], rax
0x1400019d0  movzx   eax, byte ptr [r13+5Ch]
0x1400019d5  mov     [rsi+28h], al
0x1400019d8  mov     rax, [rsp+0B8h+var_88]
0x1400019dd  mov     ecx, ebp
0x1400019df  add     rax, rcx
0x1400019e2  mov     [rsi+30h], rax
0x1400019e6  lea     r11, [rcx+rbx]
0x1400019ea  mov     [rsi+40h], r11
0x1400019ee  mov     rax, r11
0x1400019f1  mov     ecx, [r12+4]
0x1400019f6  cqo
0x1400019f8  mov     [rsi+48h], ecx
0x1400019fb  mov     r8d, [r12]
0x1400019ff  idiv    r8
0x140001a02  test    rdx, rdx
0x140001a05  jle     loc_140001C35
0x140001a0b  sub     r8d, edx
0x140001a0e  mov     [rsi+48h], r8d
0x140001a12  mov     ecx, r15d
0x140001a15  sub     ecx, ebp
0x140001a17  cmp     r8d, ecx
0x140001a1a  jbe     short loc_140001A1F
0x140001a1c  mov     [rsi+48h], ecx
0x140001a1f  mov     qword ptr [rsi+4Ch], 0
0x140001a27  lea     rax, [rsp+0B8h+Event]
0x140001a2c  mov     [rsi+58h], rax
0x140001a30  test    rdi, rdi
0x140001a33  jz      loc_140001C28
0x140001a39  mov     ecx, [r12]
0x140001a3d  mov     rax, r11
0x140001a40  cqo
0x140001a42  mov     r9, r14
0x140001a45  idiv    rcx
0x140001a48  mov     r10, r14
0x140001a4b  mov     r12, rax
0x140001a4e  mov     eax, 4EC4EC4Fh
0x140001a53  mul     r12d
0x140001a56  shr     edx, 2
0x140001a59  imul    ecx, edx, 0Dh
0x140001a5c  mov     r11d, edx
0x140001a5f  shl     r11, 4
0x140001a63  sub     r12d, ecx
0x140001a66  mov     ecx, edx
0x140001a68  shl     rcx, 5
0x140001a6c  mov     edx, r14d
0x140001a6f  mov     r13, [rcx+rdi]
0x140001a73  cmp     r12d, 2
0x140001a77  jb      short loc_140001AA6
0x140001a79  lea     r8, [r11+4]
0x140001a7d  lea     r14d, [r12-1]
0x140001a82  mov     eax, edx
0x140001a84  lea     ecx, [rdx+1]
0x140001a87  add     rax, r8
0x140001a8a  add     rcx, r8
0x140001a8d  add     edx, 2
0x140001a90  movzx   eax, word ptr [rdi+rax*2]
0x140001a94  add     r9, rax
0x140001a97  movzx   eax, word ptr [rdi+rcx*2]
0x140001a9b  add     r10, rax
0x140001a9e  cmp     edx, r14d
0x140001aa1  jb      short loc_140001A82
0x140001aa3  xor     r14d, r14d
0x140001aa6  cmp     edx, r12d
0x140001aa9  jb      loc_140001B72
0x140001aaf  add     r10, r9
0x140001ab2  mov     eax, 4EC4EC4Fh
0x140001ab7  mul     [rsp+0B8h+arg_8]
0x140001abe  mov     r9d, [rsp+0B8h+arg_8]
0x140001ac6  add     r10, r13
0x140001ac9  shr     edx, 2
0x140001acc  imul    eax, edx, 0Dh
0x140001acf  mov     r8d, edx
0x140001ad2  sub     r9d, eax
0x140001ad5  mov     eax, edx
0x140001ad7  shl     rax, 5
0x140001adb  mov     rdx, [rax+rdi]
0x140001adf  mov     eax, r14d
0x140001ae2  test    r9d, r9d
0x140001ae5  jz      short loc_140001B03
0x140001ae7  shl     r8, 4
0x140001aeb  add     r8, 4
0x140001aef  nop
0x140001af0  mov     ecx, eax
0x140001af2  inc     eax
0x140001af4  add     rcx, r8
0x140001af7  movzx   ecx, word ptr [rdi+rcx*2]
0x140001afb  add     rdx, rcx
0x140001afe  cmp     eax, r9d
0x140001b01  jb      short loc_140001AF0
0x140001b03  mov     rcx, [rsp+0B8h+arg_10]
0x140001b0b  sub     r10, rdx
0x140001b0e  mov     r13, [rsp+0B8h+arg_0]
0x140001b16  mov     r12, [rsp+0B8h+var_80]
0x140001b1b  mov     eax, r10d
0x140001b1e  add     rcx, rax
0x140001b21  mov     [rsi+38h], rcx
0x140001b25  add     ebp, [rsi+48h]
0x140001b28  lock inc cs:WimPostedReads
0x140001b2f  cmp     ebp, r15d
0x140001b32  jnb     short loc_140001B57
0x140001b34  mov     rax, cs:ExTryQueueWorkItemWrapper
0x140001b3b  test    rax, rax
0x140001b3e  jz      short loc_140001B57
0x140001b40  mov     edx, [r13+60h]
0x140001b44  mov     rcx, rsi
0x140001b47  add     edx, 20h ; ' '
0x140001b4a  call    _guard_dispatch_icall
0x140001b4f  test    al, al
0x140001b51  jnz     loc_140001980
0x140001b57  lock dec cs:WimPostedReads
0x140001b5e  lock inc cs:WimInlineReads
0x140001b65  mov     rcx, rsi; Entry
0x140001b68  call    FileProvDecompressChunks
0x140001b6d  jmp     loc_140001980
0x140001b72  mov     eax, edx
0x140001b74  add     rax, r11
0x140001b77  movzx   eax, word ptr [rdi+rax*2+8]
0x140001b7c  add     r13, rax
0x140001b7f  jmp     loc_140001AAF
0x140001b84  mov     eax, 0FFFFFFFFh
0x140001b89  lock xadd dword ptr [rsp+0B8h+Event], eax
0x140001b8f  mov     r12, [rsp+0B8h+var_28]
0x140001b97  mov     rbp, [rsp+0B8h+var_10]
0x140001b9f  cmp     eax, 1
0x140001ba2  jnz     short loc_140001BBA
0x140001ba4  xor     r8d, r8d; Wait
0x140001ba7  lea     rcx, [rsp+0B8h+Event+8]; Event
0x140001bac  xor     edx, edx; Increment
0x140001bae  call    cs:__imp_KeSetEvent
0x140001bb5  nop     dword ptr [rax+rax+00h]
0x140001bba  xor     r9d, r9d; Alertable
0x140001bbd  mov     [rsp+0B8h+Timeout], r14; Timeout
0x140001bc2  xor     r8d, r8d; WaitMode
0x140001bc5  lea     rcx, [rsp+0B8h+Event+8]; Object
0x140001bca  xor     edx, edx; WaitReason
0x140001bcc  call    cs:__imp_KeWaitForSingleObject
0x140001bd3  nop     dword ptr [rax+rax+00h]
0x140001bd8  mov     edx, dword ptr [rsp+0B8h+var_58+4]
0x140001bdc  mov     ebx, dword ptr [rsp+0B8h+var_58]
0x140001be0  mov     r14, [rsp+0B8h+var_38]
0x140001be8  mov     r8d, ebx
0x140001beb  mov     rcx, r13; Entry
0x140001bee  call    FileProvCompleteRead
0x140001bf3  mov     rcx, cs:WPP_GLOBAL_Control
0x140001bfa  mov     r15, [rsp+0B8h+var_40]
0x140001bff  mov     r13, [rsp+0B8h+var_30]
0x140001c07  mov     rdi, [rsp+0B8h+var_20]
0x140001c0f  mov     eax, [rcx+2Ch]
0x140001c12  mov     rsi, [rsp+0B8h+var_18]
0x140001c1a  test    al, 20h
0x140001c1c  jnz     short loc_140001C74
0x140001c1e  add     rsp, 0B0h
0x140001c25  pop     rbx
0x140001c26  retn
0x140001c28  mov     rcx, [rsp+0B8h+arg_10]
0x140001c30  jmp     loc_140001B21
0x140001c35  mov     r8d, ecx
0x140001c38  jmp     loc_140001A12
0x140001c3d  xor     ebx, ebx
0x140001c3f  mov     edx, ebx
0x140001c41  jmp     short loc_140001BE8
0x140001c43  cmp     byte ptr [rcx+29h], 4
0x140001c47  jb      loc_14000191A
0x140001c4d  mov     rcx, [rcx+18h]
0x140001c51  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140001c58  mov     edx, 14h
0x140001c5d  call    WPP_SF_
0x140001c62  jmp     loc_14000191A
0x140001c67  mov     dword ptr [rsp+0B8h+var_58], 0C000009Ah
0x140001c6f  jmp     loc_140001B84
0x140001c74  cmp     byte ptr [rcx+29h], 4
0x140001c78  jb      short loc_140001C1E
0x140001c7a  mov     rcx, [rcx+18h]
0x140001c7e  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140001c85  mov     edx, 15h
0x140001c8a  mov     r9d, ebx
0x140001c8d  call    WPP_SF_d
0x140001c92  jmp     short loc_140001C1E
```
