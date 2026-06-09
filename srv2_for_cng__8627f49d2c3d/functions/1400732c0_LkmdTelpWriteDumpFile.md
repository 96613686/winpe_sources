# LkmdTelpWriteDumpFile

- ea: `0x1400732c0`
- end: `0x14007349d`
- name: `LkmdTelpWriteDumpFile`
- size: `477`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400731a0`

## callees

- `0x1400732c0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140073485`
- `ntoskrnl!ZwClose` at `0x140073485`
- `ntoskrnl!ZwWriteFile` at `0x14007339c`
- `ntoskrnl!ZwWriteFile` at `0x1400733eb`
- `ntoskrnl!ZwWriteFile` at `0x14007342d`
- `ntoskrnl!ZwWriteFile` at `0x14007346e`
- `ntoskrnl!ZwWriteFile` at `0x14007339c`
- `ntoskrnl!ZwWriteFile` at `0x1400733eb`
- `ntoskrnl!ZwWriteFile` at `0x14007342d`
- `ntoskrnl!ZwWriteFile` at `0x14007346e`
- `ntoskrnl!NtBuildNumber` at `0x140073333`
- `ntoskrnl!DbgPrintEx` at `0x140073305`
- `ntoskrnl!DbgPrintEx` at `0x140073305`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelOpenDumpFile` at `0x1400732e4`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelOpenDumpFile` at `0x1400732e4`

## string_xrefs

- `0x1400732f9`: `LKMDTEL: LkmdTelpWriteDumpFile: WerLiveKernelOpenDumpFile failed, status 0x%X\n`

## pseudocode

```c
__int64 __fastcall LkmdTelpWriteDumpFile(__int64 a1)
{
  __int64 v2; // rcx
  int v3; // eax
  NTSTATUS v4; // edi
  int v5; // eax
  __int128 v6; // xmm0
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF
  HANDLE FileHandle; // [rsp+90h] [rbp+28h] BYREF

  v2 = *(_QWORD *)(a1 + 96);
  IoStatusBlock = 0;
  FileHandle = 0;
  v3 = WerLiveKernelOpenDumpFile(v2, &FileHandle);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v5 = *(_DWORD *)(a1 + 24);
    if ( v5 && *(_QWORD *)(a1 + 16) )
    {
      *(_QWORD *)(*(_QWORD *)a1 + 4000LL) = (unsigned int)(v5 + 262192);
      *(_DWORD *)(a1 + 44) = 1886221636;
      *(_DWORD *)(a1 + 48) = 1651469378;
      *(_DWORD *)(a1 + 52) = 16;
      *(_DWORD *)(a1 + 56) = NtBuildNumber;
      *(_DWORD *)(a1 + 60) = 32;
      v6 = *(_OWORD *)(a1 + 28);
      *(_QWORD *)(a1 + 84) = 0;
      *(_OWORD *)(a1 + 64) = v6;
      *(_DWORD *)(a1 + 80) = *(_DWORD *)(a1 + 24);
    }
    v4 = ZwWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, *(PVOID *)a1, *(_DWORD *)(a1 + 8), 0, 0);
    if ( v4 >= 0 )
    {
      if ( *(_DWORD *)(a1 + 24) )
      {
        v4 = ZwWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, (PVOID)(a1 + 44), 0x10u, 0, 0);
        if ( v4 >= 0 )
        {
          v4 = ZwWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, (PVOID)(a1 + 60), 0x20u, 0, 0);
          if ( v4 >= 0 )
            v4 = ZwWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, *(PVOID *)(a1 + 16), *(_DWORD *)(a1 + 24), 0, 0);
        }
      }
    }
  }
  else
  {
    DbgPrintEx(5u, 0, "LKMDTEL: LkmdTelpWriteDumpFile: WerLiveKernelOpenDumpFile failed, status 0x%X\n", v3);
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400732c0  push    rbp
0x1400732c2  push    rbx
0x1400732c3  push    rsi
0x1400732c4  push    rdi
0x1400732c5  mov     rbp, rsp
0x1400732c8  sub     rsp, 68h
0x1400732cc  mov     rbx, rcx
0x1400732cf  lea     rdx, [rbp+FileHandle]
0x1400732d3  mov     rcx, [rcx+60h]
0x1400732d7  xorps   xmm0, xmm0
0x1400732da  xor     esi, esi
0x1400732dc  movups  xmmword ptr [rbp+var_18], xmm0
0x1400732e0  mov     [rbp+FileHandle], rsi
0x1400732e4  call    cs:__imp_WerLiveKernelOpenDumpFile
0x1400732eb  nop     dword ptr [rax+rax+00h]
0x1400732f0  mov     edi, eax
0x1400732f2  test    eax, eax
0x1400732f4  jns     short loc_140073316
0x1400732f6  mov     r9d, eax
0x1400732f9  lea     r8, aLkmdtelLkmdtel_1; "LKMDTEL: LkmdTelpWriteDumpFile: WerLive"...
0x140073300  xor     edx, edx; Level
0x140073302  lea     ecx, [rsi+5]; ComponentId
0x140073305  call    cs:__imp_DbgPrintEx
0x14007330c  nop     dword ptr [rax+rax+00h]
0x140073311  jmp     loc_14007347C
0x140073316  mov     eax, [rbx+18h]
0x140073319  test    eax, eax
0x14007331b  jz      short loc_14007336E
0x14007331d  cmp     [rbx+10h], rsi
0x140073321  jz      short loc_14007336E
0x140073323  lea     ecx, [rax+40030h]
0x140073329  mov     rax, [rbx]
0x14007332c  mov     [rax+0FA0h], rcx
0x140073333  mov     rax, cs:NtBuildNumber
0x14007333a  mov     dword ptr [rbx+2Ch], 706D7544h
0x140073341  mov     dword ptr [rbx+30h], 626F6C42h
0x140073348  mov     dword ptr [rbx+34h], 10h
0x14007334f  mov     ecx, [rax]
0x140073351  mov     [rbx+38h], ecx
0x140073354  mov     dword ptr [rbx+3Ch], 20h ; ' '
0x14007335b  movups  xmm0, xmmword ptr [rbx+1Ch]
0x14007335f  mov     [rbx+54h], rsi
0x140073363  movdqu  xmmword ptr [rbx+40h], xmm0
0x140073368  mov     eax, [rbx+18h]
0x14007336b  mov     [rbx+50h], eax
0x14007336e  mov     eax, [rbx+8]
0x140073371  xor     r9d, r9d; ApcContext
0x140073374  mov     rcx, [rbp+FileHandle]; FileHandle
0x140073378  xor     r8d, r8d; ApcRoutine
0x14007337b  mov     [rsp+68h+Key], rsi; Key
0x140073380  xor     edx, edx; Event
0x140073382  mov     [rsp+68h+ByteOffset], rsi; ByteOffset
0x140073387  mov     [rsp+68h+Length], eax; Length
0x14007338b  mov     rax, [rbx]
0x14007338e  mov     [rsp+68h+Buffer], rax; Buffer
0x140073393  lea     rax, [rbp+var_18]
0x140073397  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x14007339c  call    cs:__imp_ZwWriteFile
0x1400733a3  nop     dword ptr [rax+rax+00h]
0x1400733a8  mov     edi, eax
0x1400733aa  test    eax, eax
0x1400733ac  js      loc_14007347C
0x1400733b2  cmp     [rbx+18h], esi
0x1400733b5  jbe     loc_14007347C
0x1400733bb  mov     rcx, [rbp+FileHandle]; FileHandle
0x1400733bf  lea     rax, [rbx+2Ch]
0x1400733c3  mov     [rsp+68h+Key], rsi; Key
0x1400733c8  xor     r9d, r9d; ApcContext
0x1400733cb  mov     [rsp+68h+ByteOffset], rsi; ByteOffset
0x1400733d0  xor     r8d, r8d; ApcRoutine
0x1400733d3  mov     [rsp+68h+Length], 10h; Length
0x1400733db  xor     edx, edx; Event
0x1400733dd  mov     [rsp+68h+Buffer], rax; Buffer
0x1400733e2  lea     rax, [rbp+var_18]
0x1400733e6  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x1400733eb  call    cs:__imp_ZwWriteFile
0x1400733f2  nop     dword ptr [rax+rax+00h]
0x1400733f7  mov     edi, eax
0x1400733f9  test    eax, eax
0x1400733fb  js      short loc_14007347C
0x1400733fd  mov     rcx, [rbp+FileHandle]; FileHandle
0x140073401  lea     rax, [rbx+3Ch]
0x140073405  mov     [rsp+68h+Key], rsi; Key
0x14007340a  xor     r9d, r9d; ApcContext
0x14007340d  mov     [rsp+68h+ByteOffset], rsi; ByteOffset
0x140073412  xor     r8d, r8d; ApcRoutine
0x140073415  mov     [rsp+68h+Length], 20h ; ' '; Length
0x14007341d  xor     edx, edx; Event
0x14007341f  mov     [rsp+68h+Buffer], rax; Buffer
0x140073424  lea     rax, [rbp+var_18]
0x140073428  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x14007342d  call    cs:__imp_ZwWriteFile
0x140073434  nop     dword ptr [rax+rax+00h]
0x140073439  mov     edi, eax
0x14007343b  test    eax, eax
0x14007343d  js      short loc_14007347C
0x14007343f  mov     eax, [rbx+18h]
0x140073442  xor     r9d, r9d; ApcContext
0x140073445  mov     rcx, [rbp+FileHandle]; FileHandle
0x140073449  xor     r8d, r8d; ApcRoutine
0x14007344c  mov     [rsp+68h+Key], rsi; Key
0x140073451  xor     edx, edx; Event
0x140073453  mov     [rsp+68h+ByteOffset], rsi; ByteOffset
0x140073458  mov     [rsp+68h+Length], eax; Length
0x14007345c  mov     rax, [rbx+10h]
0x140073460  mov     [rsp+68h+Buffer], rax; Buffer
0x140073465  lea     rax, [rbp+var_18]
0x140073469  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x14007346e  call    cs:__imp_ZwWriteFile
0x140073475  nop     dword ptr [rax+rax+00h]
0x14007347a  mov     edi, eax
0x14007347c  mov     rcx, [rbp+FileHandle]; Handle
0x140073480  test    rcx, rcx
0x140073483  jz      short loc_140073491
0x140073485  call    cs:__imp_ZwClose
0x14007348c  nop     dword ptr [rax+rax+00h]
0x140073491  mov     eax, edi
0x140073493  add     rsp, 68h
0x140073497  pop     rdi
0x140073498  pop     rsi
0x140073499  pop     rbx
0x14007349a  pop     rbp
0x14007349b  retn
```
