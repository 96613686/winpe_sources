# LkmdTelpWriteDumpFile

- ea: `0x140073310`
- end: `0x1400734ed`
- name: `LkmdTelpWriteDumpFile`
- size: `477`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400731f0`

## callees

- `0x140073310`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400734d5`
- `ntoskrnl!ZwClose` at `0x1400734d5`
- `ntoskrnl!ZwWriteFile` at `0x1400733ec`
- `ntoskrnl!ZwWriteFile` at `0x14007343b`
- `ntoskrnl!ZwWriteFile` at `0x14007347d`
- `ntoskrnl!ZwWriteFile` at `0x1400734be`
- `ntoskrnl!ZwWriteFile` at `0x1400733ec`
- `ntoskrnl!ZwWriteFile` at `0x14007343b`
- `ntoskrnl!ZwWriteFile` at `0x14007347d`
- `ntoskrnl!ZwWriteFile` at `0x1400734be`
- `ntoskrnl!NtBuildNumber` at `0x140073383`
- `ntoskrnl!DbgPrintEx` at `0x140073355`
- `ntoskrnl!DbgPrintEx` at `0x140073355`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelOpenDumpFile` at `0x140073334`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelOpenDumpFile` at `0x140073334`

## string_xrefs

- `0x140073349`: `LKMDTEL: LkmdTelpWriteDumpFile: WerLiveKernelOpenDumpFile failed, status 0x%X\n`

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
0x140073310  push    rbp
0x140073312  push    rbx
0x140073313  push    rsi
0x140073314  push    rdi
0x140073315  mov     rbp, rsp
0x140073318  sub     rsp, 68h
0x14007331c  mov     rbx, rcx
0x14007331f  lea     rdx, [rbp+FileHandle]
0x140073323  mov     rcx, [rcx+60h]
0x140073327  xorps   xmm0, xmm0
0x14007332a  xor     esi, esi
0x14007332c  movups  xmmword ptr [rbp+var_18], xmm0
0x140073330  mov     [rbp+FileHandle], rsi
0x140073334  call    cs:__imp_WerLiveKernelOpenDumpFile
0x14007333b  nop     dword ptr [rax+rax+00h]
0x140073340  mov     edi, eax
0x140073342  test    eax, eax
0x140073344  jns     short loc_140073366
0x140073346  mov     r9d, eax
0x140073349  lea     r8, aLkmdtelLkmdtel_1; "LKMDTEL: LkmdTelpWriteDumpFile: WerLive"...
0x140073350  xor     edx, edx; Level
0x140073352  lea     ecx, [rsi+5]; ComponentId
0x140073355  call    cs:__imp_DbgPrintEx
0x14007335c  nop     dword ptr [rax+rax+00h]
0x140073361  jmp     loc_1400734CC
0x140073366  mov     eax, [rbx+18h]
0x140073369  test    eax, eax
0x14007336b  jz      short loc_1400733BE
0x14007336d  cmp     [rbx+10h], rsi
0x140073371  jz      short loc_1400733BE
0x140073373  lea     ecx, [rax+40030h]
0x140073379  mov     rax, [rbx]
0x14007337c  mov     [rax+0FA0h], rcx
0x140073383  mov     rax, cs:NtBuildNumber
0x14007338a  mov     dword ptr [rbx+2Ch], 706D7544h
0x140073391  mov     dword ptr [rbx+30h], 626F6C42h
0x140073398  mov     dword ptr [rbx+34h], 10h
0x14007339f  mov     ecx, [rax]
0x1400733a1  mov     [rbx+38h], ecx
0x1400733a4  mov     dword ptr [rbx+3Ch], 20h ; ' '
0x1400733ab  movups  xmm0, xmmword ptr [rbx+1Ch]
0x1400733af  mov     [rbx+54h], rsi
0x1400733b3  movdqu  xmmword ptr [rbx+40h], xmm0
0x1400733b8  mov     eax, [rbx+18h]
0x1400733bb  mov     [rbx+50h], eax
0x1400733be  mov     eax, [rbx+8]
0x1400733c1  xor     r9d, r9d; ApcContext
0x1400733c4  mov     rcx, [rbp+FileHandle]; FileHandle
0x1400733c8  xor     r8d, r8d; ApcRoutine
0x1400733cb  mov     [rsp+68h+Key], rsi; Key
0x1400733d0  xor     edx, edx; Event
0x1400733d2  mov     [rsp+68h+ByteOffset], rsi; ByteOffset
0x1400733d7  mov     [rsp+68h+Length], eax; Length
0x1400733db  mov     rax, [rbx]
0x1400733de  mov     [rsp+68h+Buffer], rax; Buffer
0x1400733e3  lea     rax, [rbp+var_18]
0x1400733e7  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x1400733ec  call    cs:__imp_ZwWriteFile
0x1400733f3  nop     dword ptr [rax+rax+00h]
0x1400733f8  mov     edi, eax
0x1400733fa  test    eax, eax
0x1400733fc  js      loc_1400734CC
0x140073402  cmp     [rbx+18h], esi
0x140073405  jbe     loc_1400734CC
0x14007340b  mov     rcx, [rbp+FileHandle]; FileHandle
0x14007340f  lea     rax, [rbx+2Ch]
0x140073413  mov     [rsp+68h+Key], rsi; Key
0x140073418  xor     r9d, r9d; ApcContext
0x14007341b  mov     [rsp+68h+ByteOffset], rsi; ByteOffset
0x140073420  xor     r8d, r8d; ApcRoutine
0x140073423  mov     [rsp+68h+Length], 10h; Length
0x14007342b  xor     edx, edx; Event
0x14007342d  mov     [rsp+68h+Buffer], rax; Buffer
0x140073432  lea     rax, [rbp+var_18]
0x140073436  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x14007343b  call    cs:__imp_ZwWriteFile
0x140073442  nop     dword ptr [rax+rax+00h]
0x140073447  mov     edi, eax
0x140073449  test    eax, eax
0x14007344b  js      short loc_1400734CC
0x14007344d  mov     rcx, [rbp+FileHandle]; FileHandle
0x140073451  lea     rax, [rbx+3Ch]
0x140073455  mov     [rsp+68h+Key], rsi; Key
0x14007345a  xor     r9d, r9d; ApcContext
0x14007345d  mov     [rsp+68h+ByteOffset], rsi; ByteOffset
0x140073462  xor     r8d, r8d; ApcRoutine
0x140073465  mov     [rsp+68h+Length], 20h ; ' '; Length
0x14007346d  xor     edx, edx; Event
0x14007346f  mov     [rsp+68h+Buffer], rax; Buffer
0x140073474  lea     rax, [rbp+var_18]
0x140073478  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x14007347d  call    cs:__imp_ZwWriteFile
0x140073484  nop     dword ptr [rax+rax+00h]
0x140073489  mov     edi, eax
0x14007348b  test    eax, eax
0x14007348d  js      short loc_1400734CC
0x14007348f  mov     eax, [rbx+18h]
0x140073492  xor     r9d, r9d; ApcContext
0x140073495  mov     rcx, [rbp+FileHandle]; FileHandle
0x140073499  xor     r8d, r8d; ApcRoutine
0x14007349c  mov     [rsp+68h+Key], rsi; Key
0x1400734a1  xor     edx, edx; Event
0x1400734a3  mov     [rsp+68h+ByteOffset], rsi; ByteOffset
0x1400734a8  mov     [rsp+68h+Length], eax; Length
0x1400734ac  mov     rax, [rbx+10h]
0x1400734b0  mov     [rsp+68h+Buffer], rax; Buffer
0x1400734b5  lea     rax, [rbp+var_18]
0x1400734b9  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x1400734be  call    cs:__imp_ZwWriteFile
0x1400734c5  nop     dword ptr [rax+rax+00h]
0x1400734ca  mov     edi, eax
0x1400734cc  mov     rcx, [rbp+FileHandle]; Handle
0x1400734d0  test    rcx, rcx
0x1400734d3  jz      short loc_1400734E1
0x1400734d5  call    cs:__imp_ZwClose
0x1400734dc  nop     dword ptr [rax+rax+00h]
0x1400734e1  mov     eax, edi
0x1400734e3  add     rsp, 68h
0x1400734e7  pop     rdi
0x1400734e8  pop     rsi
0x1400734e9  pop     rbx
0x1400734ea  pop     rbp
0x1400734eb  retn
```
