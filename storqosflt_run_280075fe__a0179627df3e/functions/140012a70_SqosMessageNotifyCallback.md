# SqosMessageNotifyCallback

- ea: `0x140012a70`
- end: `0x140012c71`
- name: `SqosMessageNotifyCallback`
- size: `513`
- prototype: `NTSTATUS __stdcall(PVOID PortCookie, PVOID InputBuffer, ULONG InputBufferLength, PVOID OutputBuffer, ULONG OutputBufferLength, PULONG ReturnOutputBufferLength)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000666c`
- `0x140008250`
- `0x140008368`
- `0x140011f10`
- `0x140012a70`
- `0x140015570`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x140012af9`
- `ntoskrnl!ProbeForWrite` at `0x140012af9`
- `ntoskrnl!ProbeForRead` at `0x140012ad8`
- `ntoskrnl!ProbeForRead` at `0x140012ad8`

## pseudocode

```c
__int64 __fastcall SqosMessageNotifyCallback(
        PVOID PortCookie,
        PVOID InputBuffer,
        __int64 InputBufferLength,
        PVOID OutputBuffer,
        ULONG OutputBufferLength,
        PULONG ReturnOutputBufferLength)
{
  SIZE_T v7; // rsi
  _OWORD *v9; // rax
  unsigned __int16 *v10; // rcx
  __int64 v11; // rdx
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // r9
  __int64 v14; // rdx
  unsigned int v15; // ebx
  unsigned __int16 v17; // [rsp+30h] [rbp-238h] BYREF
  unsigned int v18; // [rsp+34h] [rbp-234h]

  v7 = (unsigned int)InputBufferLength;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 67, InputBufferLength, PortCookie);
  }
  if ( !InputBuffer || (unsigned int)v7 < 0x210 )
    goto LABEL_25;
  ProbeForRead(InputBuffer, v7, 8u);
  if ( OutputBuffer )
    ProbeForWrite(OutputBuffer, OutputBufferLength, 8u);
  v9 = InputBuffer;
  v10 = &v17;
  v11 = 4;
  do
  {
    *(_OWORD *)v10 = *v9;
    *((_OWORD *)v10 + 1) = v9[1];
    *((_OWORD *)v10 + 2) = v9[2];
    *((_OWORD *)v10 + 3) = v9[3];
    *((_OWORD *)v10 + 4) = v9[4];
    *((_OWORD *)v10 + 5) = v9[5];
    *((_OWORD *)v10 + 6) = v9[6];
    *((_OWORD *)v10 + 7) = v9[7];
    v10 += 64;
    v9 += 8;
    --v11;
  }
  while ( v11 );
  *(_OWORD *)v10 = *v9;
  if ( v17 != 257 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_25;
    }
    v13 = v17;
    v14 = 68;
LABEL_16:
    WPP_SF_D(v12->AttachedDevice, v14, 128, v13);
LABEL_25:
    v15 = -1073741811;
    goto LABEL_26;
  }
  v13 = v18;
  if ( v18 == 2 )
  {
    v15 = SqospHandleVolumeStatsRequest(
            InputBuffer,
            (unsigned int)v7,
            OutputBuffer,
            OutputBufferLength,
            ReturnOutputBufferLength);
  }
  else
  {
    if ( v18 != 4 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_25;
      }
      v14 = 69;
      goto LABEL_16;
    }
    v15 = SqospHandleVolumeThroughputAllocation(InputBuffer, v7);
    *ReturnOutputBufferLength = 0;
  }
LABEL_26:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_97d16c38264433ff5e04fa48b3a3652b_Traceguids, v15);
  }
  return v15;
}

```

## disassembly

```asm
0x140012a70  push    rbx
0x140012a72  push    rsi
0x140012a73  push    rdi
0x140012a74  push    r14
0x140012a76  sub     rsp, 248h
0x140012a7d  mov     r14, r9
0x140012a80  mov     esi, r8d
0x140012a83  mov     rbx, rdx
0x140012a86  mov     r9, rcx
0x140012a89  lea     rdi, WPP_GLOBAL_Control
0x140012a90  mov     rcx, cs:WPP_GLOBAL_Control
0x140012a97  cmp     rcx, rdi
0x140012a9a  jz      short loc_140012AB7
0x140012a9c  mov     eax, [rcx+2Ch]
0x140012a9f  test    al, 2
0x140012aa1  jz      short loc_140012AB7
0x140012aa3  cmp     byte ptr [rcx+29h], 5
0x140012aa7  jb      short loc_140012AB7
0x140012aa9  mov     edx, 43h ; 'C'
0x140012aae  mov     rcx, [rcx+18h]
0x140012ab2  call    WPP_SF_q
0x140012ab7  test    rbx, rbx
0x140012aba  jz      loc_140012C2B
0x140012ac0  cmp     esi, 210h
0x140012ac6  jb      loc_140012C2B
0x140012acc  mov     rdx, rsi; Length
0x140012acf  mov     r8d, 8; Alignment
0x140012ad5  mov     rcx, rbx; Address
0x140012ad8  call    cs:__imp_ProbeForRead
0x140012adf  nop     dword ptr [rax+rax+00h]
0x140012ae4  test    r14, r14
0x140012ae7  jz      short loc_140012B05
0x140012ae9  mov     edx, dword ptr [rsp+268h+Length]; Length
0x140012af0  mov     r8d, 8; Alignment
0x140012af6  mov     rcx, r14; Address
0x140012af9  call    cs:__imp_ProbeForWrite
0x140012b00  nop     dword ptr [rax+rax+00h]
0x140012b05  mov     rax, rbx
0x140012b08  lea     rcx, [rsp+268h+var_238]
0x140012b0d  mov     edx, 4
0x140012b12  lea     r8d, [rdx+7Ch]
0x140012b16  movups  xmm0, xmmword ptr [rax]
0x140012b19  movups  xmmword ptr [rcx], xmm0
0x140012b1c  movups  xmm1, xmmword ptr [rax+10h]
0x140012b20  movups  xmmword ptr [rcx+10h], xmm1
0x140012b24  movups  xmm0, xmmword ptr [rax+20h]
0x140012b28  movups  xmmword ptr [rcx+20h], xmm0
0x140012b2c  movups  xmm1, xmmword ptr [rax+30h]
0x140012b30  movups  xmmword ptr [rcx+30h], xmm1
0x140012b34  movups  xmm0, xmmword ptr [rax+40h]
0x140012b38  movups  xmmword ptr [rcx+40h], xmm0
0x140012b3c  movups  xmm1, xmmword ptr [rax+50h]
0x140012b40  movups  xmmword ptr [rcx+50h], xmm1
0x140012b44  movups  xmm0, xmmword ptr [rax+60h]
0x140012b48  movups  xmmword ptr [rcx+60h], xmm0
0x140012b4c  movups  xmm1, xmmword ptr [rax+70h]
0x140012b50  movups  xmmword ptr [rcx+70h], xmm1
0x140012b54  add     rcx, r8
0x140012b57  add     rax, r8
0x140012b5a  sub     rdx, 1
0x140012b5e  jnz     short loc_140012B16
0x140012b60  movups  xmm0, xmmword ptr [rax]
0x140012b63  movups  xmmword ptr [rcx], xmm0
0x140012b66  mov     eax, 101h
0x140012b6b  cmp     [rsp+268h+var_238], ax
0x140012b70  jz      short loc_140012BAD
0x140012b72  mov     rcx, cs:WPP_GLOBAL_Control
0x140012b79  cmp     rcx, rdi
0x140012b7c  jz      loc_140012C2B
0x140012b82  mov     eax, [rcx+2Ch]
0x140012b85  test    al, 40h
0x140012b87  jz      loc_140012C2B
0x140012b8d  cmp     byte ptr [rcx+29h], 2
0x140012b91  jb      loc_140012C2B
0x140012b97  movzx   r9d, [rsp+268h+var_238]
0x140012b9d  mov     edx, 44h ; 'D'
0x140012ba2  mov     rcx, [rcx+18h]
0x140012ba6  call    WPP_SF_D
0x140012bab  jmp     short loc_140012C2B
0x140012bad  mov     r9d, [rsp+268h+var_234]
0x140012bb2  cmp     r9d, 2
0x140012bb6  jz      short loc_140012BFA
0x140012bb8  cmp     r9d, 4
0x140012bbc  jz      short loc_140012BDE
0x140012bbe  mov     rcx, cs:WPP_GLOBAL_Control
0x140012bc5  cmp     rcx, rdi
0x140012bc8  jz      short loc_140012C2B
0x140012bca  mov     eax, [rcx+2Ch]
0x140012bcd  test    al, 40h
0x140012bcf  jz      short loc_140012C2B
0x140012bd1  cmp     byte ptr [rcx+29h], 2
0x140012bd5  jb      short loc_140012C2B
0x140012bd7  mov     edx, 45h ; 'E'
0x140012bdc  jmp     short loc_140012BA2
0x140012bde  mov     edx, esi; Length
0x140012be0  mov     rcx, rbx; VirtualAddress
0x140012be3  call    SqospHandleVolumeThroughputAllocation
0x140012be8  mov     ebx, eax
0x140012bea  mov     rcx, [rsp+268h+ReturnOutputBufferLength]
0x140012bf2  mov     dword ptr [rcx], 0
0x140012bf8  jmp     short loc_140012C30
0x140012bfa  mov     rax, [rsp+268h+ReturnOutputBufferLength]
0x140012c02  mov     [rsp+268h+var_248], rax
0x140012c07  mov     r9d, dword ptr [rsp+268h+Length]
0x140012c0f  mov     r8, r14
0x140012c12  mov     edx, esi
0x140012c14  mov     rcx, rbx
0x140012c17  call    SqospHandleVolumeStatsRequest
0x140012c1c  mov     ebx, eax
0x140012c1e  jmp     short loc_140012C30
0x140012c20  mov     ebx, eax
0x140012c22  lea     rdi, WPP_GLOBAL_Control
0x140012c29  jmp     short loc_140012C30
0x140012c2b  mov     ebx, 0C000000Dh
0x140012c30  mov     rcx, cs:WPP_GLOBAL_Control
0x140012c37  cmp     rcx, rdi
0x140012c3a  jz      short loc_140012C61
0x140012c3c  mov     eax, [rcx+2Ch]
0x140012c3f  test    al, 2
0x140012c41  jz      short loc_140012C61
0x140012c43  cmp     byte ptr [rcx+29h], 5
0x140012c47  jb      short loc_140012C61
0x140012c49  mov     edx, 46h ; 'F'
0x140012c4e  mov     r9d, ebx
0x140012c51  lea     r8, WPP_97d16c38264433ff5e04fa48b3a3652b_Traceguids
0x140012c58  mov     rcx, [rcx+18h]
0x140012c5c  call    WPP_SF_d
0x140012c61  mov     eax, ebx
0x140012c63  add     rsp, 248h
0x140012c6a  pop     r14
0x140012c6c  pop     rdi
0x140012c6d  pop     rsi
0x140012c6e  pop     rbx
0x140012c6f  retn
```
