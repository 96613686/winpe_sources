# ChClientOpenChannel

- ea: `0x140010834`
- end: `0x140010aff`
- name: `ChClientOpenChannel`
- size: `715`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1400043c8`
- `0x14000b800`

## callees

- `0x1400048dc`
- `0x14001016c`
- `0x140010834`
- `0x140010fa4`
- `0x1400112dc`
- `0x140012f18`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140010ad9`
- `ntoskrnl!ExReleaseFastMutex` at `0x140010ad9`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400108c6`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400108c6`

## pseudocode

```c
__int64 __fastcall ChClientOpenChannel(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        _OWORD *a6,
        unsigned int a7,
        char a8)
{
  __int64 v12; // rsi
  int v13; // edi
  __int64 v14; // rcx
  int v15; // eax
  __int64 SendMessageSized; // rdi
  __int64 v17; // rax
  bool v18; // zf
  _OWORD *v19; // rax
  __int64 v20; // xmm1_8
  int v22; // [rsp+60h] [rbp+8h] BYREF

  v22 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_af99634d4c5d304f7ae1df5facb85a1e_Traceguids, a1 + 48);
  }
  v12 = *(_QWORD *)(a1 + 216);
  v13 = XPartProcessorIndexToVpIndex(v12, a7, &v22);
  if ( v13 >= 0 )
  {
    ExAcquireFastMutex((PFAST_MUTEX)(v12 + 432));
    v14 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 760), 1u) & 0x1F;
    *(_DWORD *)(a1 + 16 * (v14 + 48)) = 23;
    *(_QWORD *)(a1 + 16 * v14 + 776) = MEMORY[0xFFFFF78000000008];
    v15 = *(_DWORD *)(a1 + 728);
    if ( v15 == 3 )
    {
      v13 = -1073741130;
    }
    else if ( v15 )
    {
      v13 = -1073741436;
    }
    else
    {
      SendMessageSized = ChAllocateSendMessageSized(v12, 156, 5);
      if ( SendMessageSized && (v17 = ChAllocateSendMessageSized(v12, 12, 7)) != 0 )
      {
        v18 = a8 == 0;
        *(_QWORD *)(a1 + 712) = v17;
        *(_BYTE *)(a1 + 734) = v18;
        v19 = a6;
        *(_OWORD *)(a1 + 260) = *a6;
        *(_OWORD *)(a1 + 276) = v19[1];
        *(_OWORD *)(a1 + 292) = v19[2];
        *(_OWORD *)(a1 + 308) = v19[3];
        *(_OWORD *)(a1 + 324) = v19[4];
        *(_OWORD *)(a1 + 340) = v19[5];
        *(_OWORD *)(a1 + 356) = v19[6];
        v20 = *((_QWORD *)v19 + 14);
        LODWORD(v19) = a5;
        ++*(_DWORD *)(a1 + 480);
        *(_QWORD *)(a1 + 372) = v20;
        *(_DWORD *)(a1 + 256) = (_DWORD)v19;
        *(_DWORD *)(a1 + 252) = a4;
        *(_QWORD *)(a1 + 696) = a2;
        *(_QWORD *)(a1 + 704) = a3;
        if ( *(_DWORD *)(v12 + 168) >= 0x20004u )
          *(_DWORD *)(a1 + 672) = v22;
        *(_OWORD *)(SendMessageSized + 28) = *(_OWORD *)(a1 + 260);
        *(_OWORD *)(SendMessageSized + 44) = *(_OWORD *)(a1 + 276);
        *(_OWORD *)(SendMessageSized + 60) = *(_OWORD *)(a1 + 292);
        *(_OWORD *)(SendMessageSized + 76) = *(_OWORD *)(a1 + 308);
        *(_OWORD *)(SendMessageSized + 92) = *(_OWORD *)(a1 + 324);
        *(_OWORD *)(SendMessageSized + 108) = *(_OWORD *)(a1 + 340);
        *(_OWORD *)(SendMessageSized + 124) = *(_OWORD *)(a1 + 356);
        *(_QWORD *)(SendMessageSized + 140) = *(_QWORD *)(a1 + 372);
        *(_DWORD *)(SendMessageSized + 8) = *(_DWORD *)(a1 + 24);
        *(_DWORD *)(SendMessageSized + 16) = *(_DWORD *)(a1 + 252);
        *(_DWORD *)(SendMessageSized + 24) = *(_DWORD *)(a1 + 256);
        *(_DWORD *)(SendMessageSized + 12) = *(_DWORD *)(a1 + 480);
        if ( *(_DWORD *)(v12 + 168) >= 0x20004u )
          *(_DWORD *)(SendMessageSized + 20) = v22;
        ChSendMessage(*(_QWORD *)(a1 + 216), SendMessageSized);
        ChReferenceChannelInternal(a1, 19, 472);
        v13 = 0;
        *(_DWORD *)(a1 + 728) = 1;
      }
      else
      {
        v13 = -1073741670;
      }
    }
    ExReleaseFastMutex((PFAST_MUTEX)(v12 + 432));
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140010834  mov     [rsp+arg_8], rbx
0x140010839  mov     [rsp+arg_10], rbp
0x14001083e  push    rsi
0x14001083f  push    rdi
0x140010840  push    r12
0x140010842  push    r14
0x140010844  push    r15
0x140010846  sub     rsp, 30h
0x14001084a  mov     r14d, r9d
0x14001084d  mov     [rsp+58h+arg_0], 0
0x140010855  mov     r15, r8
0x140010858  mov     r12, rdx
0x14001085b  mov     rbx, rcx
0x14001085e  mov     rcx, cs:WPP_GLOBAL_Control
0x140010865  lea     rax, WPP_GLOBAL_Control
0x14001086c  cmp     rcx, rax
0x14001086f  jz      short loc_140010897
0x140010871  mov     eax, [rcx+2Ch]
0x140010874  test    al, 40h
0x140010876  jz      short loc_140010897
0x140010878  cmp     byte ptr [rcx+29h], 5
0x14001087c  jb      short loc_140010897
0x14001087e  mov     rcx, [rcx+18h]
0x140010882  lea     r9, [rbx+30h]
0x140010886  mov     edx, 0Ah
0x14001088b  lea     r8, WPP_af99634d4c5d304f7ae1df5facb85a1e_Traceguids
0x140010892  call    WPP_SF__guid_
0x140010897  mov     rsi, [rbx+0D8h]
0x14001089e  lea     r8, [rsp+58h+arg_0]
0x1400108a3  mov     edx, [rsp+58h+arg_30]
0x1400108aa  mov     rcx, rsi
0x1400108ad  call    XPartProcessorIndexToVpIndex
0x1400108b2  mov     edi, eax
0x1400108b4  test    eax, eax
0x1400108b6  js      loc_140010AE5
0x1400108bc  lea     rbp, [rsi+1B0h]
0x1400108c3  mov     rcx, rbp; FastMutex
0x1400108c6  call    cs:__imp_ExAcquireFastMutex
0x1400108cd  nop     dword ptr [rax+rax+00h]
0x1400108d2  mov     ecx, 1
0x1400108d7  lock xadd [rbx+2F8h], ecx
0x1400108df  and     ecx, 1Fh
0x1400108e2  lea     rax, [rcx+30h]
0x1400108e6  add     rcx, rcx
0x1400108e9  add     rax, rax
0x1400108ec  mov     dword ptr [rbx+rax*8], 17h
0x1400108f3  mov     rax, ds:0FFFFF78000000008h
0x1400108fd  mov     [rbx+rcx*8+308h], rax
0x140010905  mov     eax, [rbx+2D8h]
0x14001090b  cmp     eax, 3
0x14001090e  jnz     short loc_14001091A
0x140010910  mov     edi, 0C00002B6h
0x140010915  jmp     loc_140010AD6
0x14001091a  test    eax, eax
0x14001091c  jz      short loc_140010928
0x14001091e  mov     edi, 0C0000184h
0x140010923  jmp     loc_140010AD6
0x140010928  mov     edx, 9Ch
0x14001092d  mov     r8d, 5
0x140010933  mov     rcx, rsi
0x140010936  call    ChAllocateSendMessageSized
0x14001093b  mov     rdi, rax
0x14001093e  test    rax, rax
0x140010941  jnz     short loc_14001094D
0x140010943  mov     edi, 0C000009Ah
0x140010948  jmp     loc_140010AD6
0x14001094d  mov     edx, 0Ch
0x140010952  mov     rcx, rsi
0x140010955  lea     r8d, [rdx-5]
0x140010959  call    ChAllocateSendMessageSized
0x14001095e  test    rax, rax
0x140010961  jz      short loc_140010943
0x140010963  cmp     [rsp+58h+arg_38], 0
0x14001096b  mov     ecx, 20004h
0x140010970  mov     [rbx+2C8h], rax
0x140010977  setz    al
0x14001097a  mov     [rbx+2DEh], al
0x140010980  mov     rax, [rsp+58h+arg_28]
0x140010988  movups  xmm0, xmmword ptr [rax]
0x14001098b  movups  xmmword ptr [rbx+104h], xmm0
0x140010992  movups  xmm1, xmmword ptr [rax+10h]
0x140010996  movups  xmmword ptr [rbx+114h], xmm1
0x14001099d  movups  xmm0, xmmword ptr [rax+20h]
0x1400109a1  movups  xmmword ptr [rbx+124h], xmm0
0x1400109a8  movups  xmm1, xmmword ptr [rax+30h]
0x1400109ac  movups  xmmword ptr [rbx+134h], xmm1
0x1400109b3  movups  xmm0, xmmword ptr [rax+40h]
0x1400109b7  movups  xmmword ptr [rbx+144h], xmm0
0x1400109be  movups  xmm1, xmmword ptr [rax+50h]
0x1400109c2  movups  xmmword ptr [rbx+154h], xmm1
0x1400109c9  movups  xmm0, xmmword ptr [rax+60h]
0x1400109cd  movups  xmmword ptr [rbx+164h], xmm0
0x1400109d4  movsd   xmm1, qword ptr [rax+70h]
0x1400109d9  mov     eax, [rsp+58h+arg_20]
0x1400109e0  inc     dword ptr [rbx+1E0h]
0x1400109e6  movsd   qword ptr [rbx+174h], xmm1
0x1400109ee  mov     [rbx+100h], eax
0x1400109f4  mov     [rbx+0FCh], r14d
0x1400109fb  mov     [rbx+2B8h], r12
0x140010a02  mov     [rbx+2C0h], r15
0x140010a09  cmp     [rsi+0A8h], ecx
0x140010a0f  jb      short loc_140010A1B
0x140010a11  mov     eax, [rsp+58h+arg_0]
0x140010a15  mov     [rbx+2A0h], eax
0x140010a1b  movups  xmm0, xmmword ptr [rbx+104h]
0x140010a22  movups  xmmword ptr [rdi+1Ch], xmm0
0x140010a26  movups  xmm1, xmmword ptr [rbx+114h]
0x140010a2d  movups  xmmword ptr [rdi+2Ch], xmm1
0x140010a31  movups  xmm0, xmmword ptr [rbx+124h]
0x140010a38  movups  xmmword ptr [rdi+3Ch], xmm0
0x140010a3c  movups  xmm1, xmmword ptr [rbx+134h]
0x140010a43  movups  xmmword ptr [rdi+4Ch], xmm1
0x140010a47  movups  xmm0, xmmword ptr [rbx+144h]
0x140010a4e  movups  xmmword ptr [rdi+5Ch], xmm0
0x140010a52  movups  xmm1, xmmword ptr [rbx+154h]
0x140010a59  movups  xmmword ptr [rdi+6Ch], xmm1
0x140010a5d  movups  xmm0, xmmword ptr [rbx+164h]
0x140010a64  movups  xmmword ptr [rdi+7Ch], xmm0
0x140010a68  movsd   xmm1, qword ptr [rbx+174h]
0x140010a70  movsd   qword ptr [rdi+8Ch], xmm1
0x140010a78  mov     eax, [rbx+18h]
0x140010a7b  mov     [rdi+8], eax
0x140010a7e  mov     eax, [rbx+0FCh]
0x140010a84  mov     [rdi+10h], eax
0x140010a87  mov     eax, [rbx+100h]
0x140010a8d  mov     [rdi+18h], eax
0x140010a90  mov     eax, [rbx+1E0h]
0x140010a96  mov     [rdi+0Ch], eax
0x140010a99  cmp     [rsi+0A8h], ecx
0x140010a9f  jb      short loc_140010AA8
0x140010aa1  mov     eax, [rsp+58h+arg_0]
0x140010aa5  mov     [rdi+14h], eax
0x140010aa8  mov     rcx, [rbx+0D8h]
0x140010aaf  mov     rdx, rdi
0x140010ab2  call    ChSendMessage
0x140010ab7  mov     edx, 13h
0x140010abc  mov     r8d, 1D8h
0x140010ac2  mov     rcx, rbx
0x140010ac5  call    ChReferenceChannelInternal
0x140010aca  xor     edi, edi
0x140010acc  mov     dword ptr [rbx+2D8h], 1
0x140010ad6  mov     rcx, rbp; FastMutex
0x140010ad9  call    cs:__imp_ExReleaseFastMutex
0x140010ae0  nop     dword ptr [rax+rax+00h]
0x140010ae5  mov     rbx, [rsp+58h+arg_8]
0x140010aea  mov     eax, edi
0x140010aec  mov     rbp, [rsp+58h+arg_10]
0x140010af1  add     rsp, 30h
0x140010af5  pop     r15
0x140010af7  pop     r14
0x140010af9  pop     r12
0x140010afb  pop     rdi
0x140010afc  pop     rsi
0x140010afd  retn
```
