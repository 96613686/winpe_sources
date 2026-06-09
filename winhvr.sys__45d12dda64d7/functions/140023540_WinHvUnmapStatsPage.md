# WinHvUnmapStatsPage

- ea: `0x140023540`
- end: `0x14002364c`
- name: `WinHvUnmapStatsPage`
- size: `268`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x140002240`
- `0x140003610`
- `0x140005dcc`
- `0x140007620`
- `0x140009c90`
- `0x14000a040`
- `0x14000b040`
- `0x140023540`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140023634`
- `ntoskrnl!ExReleaseFastMutex` at `0x140023634`
- `ntoskrnl!ExAcquireFastMutex` at `0x140023591`
- `ntoskrnl!ExAcquireFastMutex` at `0x140023591`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x140023621`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x140023621`
- `ntoskrnl!MmUnmapIoSpace` at `0x14002360b`
- `ntoskrnl!MmUnmapIoSpace` at `0x14002360b`

## pseudocode

```c
void __fastcall WinHvUnmapStatsPage(_DWORD **a1)
{
  _DWORD *v2; // rbx
  __int64 *v4; // rcx
  _QWORD v5[9]; // [rsp+20h] [rbp-48h] BYREF
  __int64 *v6; // [rsp+80h] [rbp+18h] BYREF

  v6 = 0;
  memset(v5, 0, 0x40u);
  if ( WinHvpConnected )
  {
    v2 = *a1;
    *a1 = 0;
    WinHvpFreePoolWithTag(a1, 1333151831);
    ExAcquireFastMutex(&WinHvpStatsTableLock);
    if ( v2[8]-- == 1 )
    {
      WinHvpSetupHypercall(&v6, 0, (__int64)v5);
      v4 = v6;
      *(_DWORD *)v6 = *v2;
      *(_OWORD *)(v4 + 1) = *(_OWORD *)(v2 + 2);
      WinHvpSimplePoolHypercall_CallViaMacro(v5[0], 109);
      ((void (__fastcall *)(_QWORD))v5[7])(v5[0]);
    }
    if ( !v2[8] )
    {
      if ( (unsigned __int8)WinHvIsOverlayMapLocationRequired() )
        WinHvpFreeOverlayPhysicalPage(*((_QWORD *)v2 + 3));
      MmUnmapIoSpace(*((PVOID *)v2 + 5), 0x1000u);
      RtlDeleteElementGenericTable(&WinHvpStatsTable, v2);
    }
    ExReleaseFastMutex(&WinHvpStatsTableLock);
  }
}

```

## disassembly

```asm
0x140023540  mov     rax, rsp
0x140023543  mov     [rax+8], rbx
0x140023547  push    rdi
0x140023548  sub     rsp, 60h
0x14002354c  xor     edx, edx; Val
0x14002354e  mov     qword ptr [rax+18h], 0
0x140023556  mov     rdi, rcx
0x140023559  lea     rcx, [rax-48h]; void *
0x14002355d  lea     r8d, [rdx+40h]; Size
0x140023561  call    memset
0x140023566  cmp     cs:WinHvpConnected, 0
0x14002356d  jz      loc_140023640
0x140023573  mov     rbx, [rdi]
0x140023576  mov     edx, 4F764857h
0x14002357b  mov     rcx, rdi
0x14002357e  mov     qword ptr [rdi], 0
0x140023585  call    WinHvpFreePoolWithTag
0x14002358a  lea     rcx, WinHvpStatsTableLock; FastMutex
0x140023591  call    cs:__imp_ExAcquireFastMutex
0x140023598  nop     dword ptr [rax+rax+00h]
0x14002359d  add     dword ptr [rbx+20h], 0FFFFFFFFh
0x1400235a1  jnz     short loc_1400235EA
0x1400235a3  lea     r8, [rsp+68h+var_48]
0x1400235a8  xor     edx, edx
0x1400235aa  lea     rcx, [rsp+68h+arg_10]
0x1400235b2  call    WinHvpSetupHypercall
0x1400235b7  mov     rcx, [rsp+68h+arg_10]
0x1400235bf  mov     edx, 6Dh ; 'm'
0x1400235c4  mov     eax, [rbx]
0x1400235c6  mov     [rcx], eax
0x1400235c8  movups  xmm0, xmmword ptr [rbx+8]
0x1400235cc  movdqu  xmmword ptr [rcx+8], xmm0
0x1400235d1  mov     rcx, [rsp+68h+var_48]
0x1400235d6  call    WinHvpSimplePoolHypercall_CallViaMacro
0x1400235db  mov     rcx, [rsp+68h+var_48]
0x1400235e0  mov     rax, [rsp+68h+var_10]
0x1400235e5  call    _guard_dispatch_icall
0x1400235ea  cmp     dword ptr [rbx+20h], 0
0x1400235ee  jnz     short loc_14002362D
0x1400235f0  call    WinHvIsOverlayMapLocationRequired
0x1400235f5  test    al, al
0x1400235f7  jz      short loc_140023602
0x1400235f9  mov     rcx, [rbx+18h]
0x1400235fd  call    WinHvpFreeOverlayPhysicalPage
0x140023602  mov     rcx, [rbx+28h]; BaseAddress
0x140023606  mov     edx, 1000h; NumberOfBytes
0x14002360b  call    cs:__imp_MmUnmapIoSpace
0x140023612  nop     dword ptr [rax+rax+00h]
0x140023617  mov     rdx, rbx; Buffer
0x14002361a  lea     rcx, WinHvpStatsTable; Table
0x140023621  call    cs:__imp_RtlDeleteElementGenericTable
0x140023628  nop     dword ptr [rax+rax+00h]
0x14002362d  lea     rcx, WinHvpStatsTableLock; FastMutex
0x140023634  call    cs:__imp_ExReleaseFastMutex
0x14002363b  nop     dword ptr [rax+rax+00h]
0x140023640  mov     rbx, [rsp+68h+arg_0]
0x140023645  add     rsp, 60h
0x140023649  pop     rdi
0x14002364a  retn
```
