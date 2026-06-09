# PgmQueryInformation

- ea: `0x14000bf5c`
- end: `0x14000c2ef`
- name: `PgmQueryInformation`
- size: `915`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140007d90`

## callees

- `0x140005038`
- `0x140005068`
- `0x1400052e4`
- `0x1400054d0`
- `0x14000bef8`
- `0x14000bf5c`
- `0x14001cdf0`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14000c180`
- `ntoskrnl!IofCallDriver` at `0x14000c2c7`
- `ntoskrnl!IofCallDriver` at `0x14000c180`
- `ntoskrnl!IofCallDriver` at `0x14000c2c7`
- `TDI!TdiCopyBufferToMdl` at `0x14000c06d`
- `TDI!TdiCopyBufferToMdl` at `0x14000c06d`

## pseudocode

```c
__int64 __fastcall PgmQueryInformation(__int64 a1, IRP *a2, __int64 a3)
{
  __int64 v3; // r9
  unsigned int v6; // ebx
  struct _MDL *MdlAddress; // rdx
  __int64 v8; // rdi
  int v9; // ecx
  NTSTATUS v10; // eax
  ULONG v11; // r8d
  __int64 v12; // r8
  struct _IO_STACK_LOCATION *v13; // rax
  struct _IO_STACK_LOCATION *v14; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v16; // rcx
  ULONG BytesCopied[4]; // [rsp+30h] [rbp-40h] BYREF
  _DWORD SourceBuffer[8]; // [rsp+40h] [rbp-30h] BYREF

  v3 = *(unsigned int *)(a3 + 8);
  BytesCopied[0] = 0;
  memset(SourceBuffer, 0, 28);
  if ( (_DWORD)v3 == 2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids);
    CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)QueryProviderCompletion;
    CurrentStackLocation[-1].Context = 0;
    CurrentStackLocation[-1].Control = -32;
    v16 = a2->Tail.Overlay.CurrentStackLocation;
    *(_WORD *)&v16[-1].MajorFunction = 3087;
    v16[-1].DeviceObject = *(PDEVICE_OBJECT *)(a1 + 48);
    v16[-1].FileObject = *(PFILE_OBJECT *)(a1 + 56);
    v16[-1].Parameters.Read.Length = 2;
    v16[-1].Parameters.QueryDirectory.FileName = 0;
    return (unsigned int)IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 48), a2);
  }
  else
  {
    if ( (_DWORD)v3 != 3 )
    {
      v6 = -1073741822;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids, v3);
      return v6;
    }
    MdlAddress = a2->MdlAddress;
    if ( MdlAddress )
    {
      v8 = *(_QWORD *)(*(_QWORD *)(a3 + 48) + 24LL);
      if ( !v8 )
        goto LABEL_24;
      v9 = *(_DWORD *)(v8 + 16);
      if ( ((v9 - 843334721) & 0xDFFFFFFF) == 0 )
      {
        SourceBuffer[0] = 1;
        *(_QWORD *)&SourceBuffer[1] = 0x2000E00000001LL;
        *(_DWORD *)((char *)&SourceBuffer[3] + 2) = _byteswap_ulong(*(_DWORD *)(v8 + 328));
        LOWORD(SourceBuffer[3]) = __ROR2__(*(_WORD *)(v8 + 332), 8);
        v10 = TdiCopyBufferToMdl(SourceBuffer, 0, 0x1Au, MdlAddress, 0, BytesCopied);
        v11 = BytesCopied[0];
        v6 = v10;
        a2->IoStatus.Information = BytesCopied[0];
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_qDD(
            WPP_GLOBAL_Control->AttachedDevice,
            16,
            WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids,
            v8,
            v11,
            26);
        }
        return v6;
      }
      if ( ((v9 - 1381188947) & 0xFEFFFFFF) != 0 )
      {
LABEL_24:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids, v8);
      }
      else
      {
        v12 = *(_QWORD *)(v8 + 24);
        if ( v12 && *(_DWORD *)(v12 + 16) == 1380205633 )
        {
          v13 = a2->Tail.Overlay.CurrentStackLocation;
          a2->MdlAddress = MdlAddress;
          v13[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)QueryAddressCompletion;
          v13[-1].Context = 0;
          v13[-1].Control = -32;
          v14 = a2->Tail.Overlay.CurrentStackLocation;
          *(_WORD *)&v14[-1].MajorFunction = 3087;
          v14[-1].DeviceObject = *(PDEVICE_OBJECT *)(v12 + 80);
          v14[-1].FileObject = *(PFILE_OBJECT *)(v12 + 72);
          v14[-1].Parameters.Read.Length = 3;
          v14[-1].Parameters.QueryDirectory.FileName = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids, v8);
          }
          IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 48), a2);
          return 259;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_qq(
            WPP_GLOBAL_Control->AttachedDevice,
            18,
            WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids,
            v8,
            *(_QWORD *)(v8 + 24));
      }
      return (unsigned int)-1073741816;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids, a2);
    return (unsigned int)-1073741823;
  }
}

```

## disassembly

```asm
0x14000bf5c  push    rbp
0x14000bf5e  push    rbx
0x14000bf5f  push    rsi
0x14000bf60  push    rdi
0x14000bf61  push    r14
0x14000bf63  mov     rbp, rsp
0x14000bf66  sub     rsp, 70h
0x14000bf6a  mov     rax, cs:__security_cookie
0x14000bf71  xor     rax, rsp
0x14000bf74  mov     [rbp+var_10], rax
0x14000bf78  mov     r9d, [r8+8]
0x14000bf7c  mov     rbx, rcx
0x14000bf7f  xorps   xmm0, xmm0
0x14000bf82  mov     [rbp+var_40], 0
0x14000bf89  mov     ecx, r9d
0x14000bf8c  mov     r14d, 2
0x14000bf92  mov     rsi, rdx
0x14000bf95  movups  xmmword ptr [rbp+SourceBuffer], xmm0
0x14000bf99  movups  xmmword ptr [rbp+SourceBuffer+0Ch], xmm0
0x14000bf9d  sub     ecx, r14d
0x14000bfa0  jz      loc_14000C24A
0x14000bfa6  cmp     ecx, 1
0x14000bfa9  jz      short loc_14000BFEC
0x14000bfab  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bfb2  lea     rax, WPP_GLOBAL_Control
0x14000bfb9  mov     ebx, 0C0000002h
0x14000bfbe  cmp     rcx, rax
0x14000bfc1  jz      loc_14000C2D5
0x14000bfc7  mov     eax, [rcx+2Ch]
0x14000bfca  test    r14b, al
0x14000bfcd  jz      loc_14000C2D5
0x14000bfd3  mov     rcx, [rcx+18h]
0x14000bfd7  lea     edx, [r14+13h]
0x14000bfdb  lea     r8, WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids
0x14000bfe2  call    WPP_SF_d
0x14000bfe7  jmp     loc_14000C2D5
0x14000bfec  mov     rdx, [rdx+8]
0x14000bff0  test    rdx, rdx
0x14000bff3  jz      loc_14000C20D
0x14000bff9  mov     rax, [r8+30h]
0x14000bffd  mov     rdi, [rax+18h]
0x14000c001  test    rdi, rdi
0x14000c004  jz      loc_14000C1D8
0x14000c00a  mov     ecx, [rdi+10h]
0x14000c00d  lea     eax, [rcx-32444441h]
0x14000c013  test    eax, 0DFFFFFFFh
0x14000c018  jnz     loc_14000C0CD
0x14000c01e  mov     eax, 1
0x14000c023  mov     dword ptr [rbp+SourceBuffer+8], 2000Eh
0x14000c02a  mov     dword ptr [rbp+SourceBuffer], eax
0x14000c02d  lea     rcx, [rbp+SourceBuffer]; SourceBuffer
0x14000c031  mov     dword ptr [rbp+SourceBuffer+4], eax
0x14000c034  mov     r9, rdx; DestinationMdlChain
0x14000c037  mov     eax, [rdi+148h]
0x14000c03d  mov     r14d, 1Ah
0x14000c043  bswap   eax
0x14000c045  mov     dword ptr [rbp+SourceBuffer+0Eh], eax
0x14000c048  mov     r8d, r14d; SourceBytesToCopy
0x14000c04b  movzx   eax, word ptr [rdi+14Ch]
0x14000c052  xor     edx, edx; SourceOffset
0x14000c054  ror     ax, 8
0x14000c058  mov     word ptr [rbp+SourceBuffer+0Ch], ax
0x14000c05c  lea     rax, [rbp+var_40]
0x14000c060  mov     [rsp+70h+BytesCopied], rax; BytesCopied
0x14000c065  mov     [rsp+70h+DestinationOffset], 0; DestinationOffset
0x14000c06d  call    cs:__imp_TdiCopyBufferToMdl
0x14000c074  nop     dword ptr [rax+rax+00h]
0x14000c079  mov     r8d, [rbp+var_40]
0x14000c07d  mov     ebx, eax
0x14000c07f  mov     [rsi+38h], r8
0x14000c083  mov     r10, cs:WPP_GLOBAL_Control
0x14000c08a  lea     rax, WPP_GLOBAL_Control
0x14000c091  cmp     r10, rax
0x14000c094  jz      loc_14000C2D5
0x14000c09a  mov     ecx, [r10+2Ch]
0x14000c09e  test    cl, 10h
0x14000c0a1  jz      loc_14000C2D5
0x14000c0a7  mov     rcx, [r10+18h]
0x14000c0ab  lea     edx, [r14-0Ah]
0x14000c0af  mov     dword ptr [rsp+70h+BytesCopied], r14d
0x14000c0b4  mov     r9, rdi
0x14000c0b7  mov     [rsp+70h+DestinationOffset], r8d
0x14000c0bc  lea     r8, WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids
0x14000c0c3  call    WPP_SF_qDD
0x14000c0c8  jmp     loc_14000C2D5
0x14000c0cd  lea     eax, [rcx-52534553h]
0x14000c0d3  test    eax, 0FEFFFFFFh
0x14000c0d8  jnz     loc_14000C1D8
0x14000c0de  mov     r8, [rdi+18h]
0x14000c0e2  test    r8, r8
0x14000c0e5  jz      loc_14000C196
0x14000c0eb  cmp     dword ptr [r8+10h], 52444441h
0x14000c0f3  jnz     loc_14000C196
0x14000c0f9  mov     rax, [rsi+0B8h]
0x14000c100  lea     rcx, QueryAddressCompletion
0x14000c107  mov     [rsi+8], rdx
0x14000c10b  mov     [rax-10h], rcx
0x14000c10f  mov     qword ptr [rax-8], 0
0x14000c117  mov     byte ptr [rax-45h], 0E0h
0x14000c11b  mov     rcx, [rsi+0B8h]
0x14000c122  mov     word ptr [rcx-48h], 0C0Fh
0x14000c128  mov     rax, [r8+50h]
0x14000c12c  mov     [rcx-20h], rax
0x14000c130  mov     rax, [r8+48h]
0x14000c134  mov     [rcx-18h], rax
0x14000c138  mov     dword ptr [rcx-40h], 3
0x14000c13f  mov     qword ptr [rcx-38h], 0
0x14000c147  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c14e  lea     rax, WPP_GLOBAL_Control
0x14000c155  cmp     rcx, rax
0x14000c158  jz      short loc_14000C179
0x14000c15a  mov     eax, [rcx+2Ch]
0x14000c15d  test    al, 10h
0x14000c15f  jz      short loc_14000C179
0x14000c161  mov     rcx, [rcx+18h]
0x14000c165  lea     r8, WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids
0x14000c16c  mov     edx, 11h
0x14000c171  mov     r9, rdi
0x14000c174  call    WPP_SF_q
0x14000c179  mov     rcx, [rbx+30h]; DeviceObject
0x14000c17d  mov     rdx, rsi; Irp
0x14000c180  call    cs:__imp_IofCallDriver
0x14000c187  nop     dword ptr [rax+rax+00h]
0x14000c18c  mov     ebx, 103h
0x14000c191  jmp     loc_14000C2D5
0x14000c196  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c19d  lea     rax, WPP_GLOBAL_Control
0x14000c1a4  cmp     rcx, rax
0x14000c1a7  jz      short loc_14000C1CE
0x14000c1a9  mov     eax, [rcx+2Ch]
0x14000c1ac  test    r14b, al
0x14000c1af  jz      short loc_14000C1CE
0x14000c1b1  mov     rcx, [rcx+18h]
0x14000c1b5  mov     edx, 12h
0x14000c1ba  mov     qword ptr [rsp+70h+DestinationOffset], r8
0x14000c1bf  mov     r9, rdi
0x14000c1c2  lea     r8, WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids
0x14000c1c9  call    WPP_SF_qq
0x14000c1ce  mov     ebx, 0C0000008h
0x14000c1d3  jmp     loc_14000C2D5
0x14000c1d8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c1df  lea     rax, WPP_GLOBAL_Control
0x14000c1e6  cmp     rcx, rax
0x14000c1e9  jz      short loc_14000C1CE
0x14000c1eb  mov     eax, [rcx+2Ch]
0x14000c1ee  test    r14b, al
0x14000c1f1  jz      short loc_14000C1CE
0x14000c1f3  mov     rcx, [rcx+18h]
0x14000c1f7  lea     r8, WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids
0x14000c1fe  mov     edx, 13h
0x14000c203  mov     r9, rdi
0x14000c206  call    WPP_SF_q
0x14000c20b  jmp     short loc_14000C1CE
0x14000c20d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c214  lea     rax, WPP_GLOBAL_Control
0x14000c21b  cmp     rcx, rax
0x14000c21e  jz      short loc_14000C240
0x14000c220  mov     eax, [rcx+2Ch]
0x14000c223  test    r14b, al
0x14000c226  jz      short loc_14000C240
0x14000c228  mov     rcx, [rcx+18h]
0x14000c22c  lea     r8, WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids
0x14000c233  mov     edx, 14h
0x14000c238  mov     r9, rsi
0x14000c23b  call    WPP_SF_q
0x14000c240  mov     ebx, 0C0000001h
0x14000c245  jmp     loc_14000C2D5
0x14000c24a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c251  lea     rax, WPP_GLOBAL_Control
0x14000c258  cmp     rcx, rax
0x14000c25b  jz      short loc_14000C279
0x14000c25d  mov     eax, [rcx+2Ch]
0x14000c260  test    al, 10h
0x14000c262  jz      short loc_14000C279
0x14000c264  mov     rcx, [rcx+18h]
0x14000c268  lea     r8, WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids
0x14000c26f  mov     edx, 0Fh
0x14000c274  call    WPP_SF_
0x14000c279  mov     rax, [rsi+0B8h]
0x14000c280  lea     rcx, QueryProviderCompletion
0x14000c287  mov     rdx, rsi; Irp
0x14000c28a  mov     [rax-10h], rcx
0x14000c28e  mov     qword ptr [rax-8], 0
0x14000c296  mov     byte ptr [rax-45h], 0E0h
0x14000c29a  mov     rcx, [rsi+0B8h]
0x14000c2a1  mov     word ptr [rcx-48h], 0C0Fh
0x14000c2a7  mov     rax, [rbx+30h]
0x14000c2ab  mov     [rcx-20h], rax
0x14000c2af  mov     rax, [rbx+38h]
0x14000c2b3  mov     [rcx-18h], rax
0x14000c2b7  mov     [rcx-40h], r14d
0x14000c2bb  mov     qword ptr [rcx-38h], 0
0x14000c2c3  mov     rcx, [rbx+30h]; DeviceObject
0x14000c2c7  call    cs:__imp_IofCallDriver
0x14000c2ce  nop     dword ptr [rax+rax+00h]
0x14000c2d3  mov     ebx, eax
0x14000c2d5  mov     eax, ebx
0x14000c2d7  mov     rcx, [rbp+var_10]
0x14000c2db  xor     rcx, rsp; StackCookie
0x14000c2de  call    __security_check_cookie
0x14000c2e3  add     rsp, 70h
0x14000c2e7  pop     r14
0x14000c2e9  pop     rdi
0x14000c2ea  pop     rsi
0x14000c2eb  pop     rbx
0x14000c2ec  pop     rbp
0x14000c2ed  retn
```
