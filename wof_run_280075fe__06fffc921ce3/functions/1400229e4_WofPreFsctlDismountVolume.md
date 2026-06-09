# WofPreFsctlDismountVolume

- ea: `0x1400229e4`
- end: `0x140022b4c`
- name: `WofPreFsctlDismountVolume`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400346f0`

## callees

- `0x1400014d0`
- `0x140011640`
- `0x1400229e4`

## import_xrefs

- `FLTMGR!FltFsControlFile` at `0x140022abc`
- `FLTMGR!FltFsControlFile` at `0x140022abc`
- `FLTMGR!FltReleaseContext` at `0x140022a74`
- `FLTMGR!FltReleaseContext` at `0x140022b2d`
- `FLTMGR!FltReleaseContext` at `0x140022a74`
- `FLTMGR!FltReleaseContext` at `0x140022b2d`

## pseudocode

```c
__int64 __fastcall WofPreFsctlDismountVolume(__int64 a1, __int64 a2)
{
  int VolumeContext; // esi
  char *v6; // rbx
  unsigned int v7; // edi
  __int64 v8; // rcx
  __int64 (__fastcall *v9)(char *); // rax
  NTSTATUS v10; // eax
  __int64 v11; // rax
  unsigned int v12; // edi
  __int64 v13; // rcx
  void (__fastcall *v14)(char *); // rax
  PFLT_CONTEXT Context; // [rsp+90h] [rbp+18h] BYREF

  Context = 0;
  VolumeContext = WofGetVolumeContext(*(PFLT_INSTANCE *)(a2 + 24), &Context);
  if ( VolumeContext < 0 )
    return 1;
  v6 = (char *)Context;
  v7 = 0;
  do
  {
    v8 = 424LL * v7;
    if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v8) )
    {
      v9 = *(__int64 (__fastcall **)(char *))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v8 + 280);
      if ( v9 )
      {
        VolumeContext = v9(&v6[*(unsigned int *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v8 + 20)]);
        if ( VolumeContext < 0 )
          break;
      }
    }
    ++v7;
  }
  while ( v7 <= *((_DWORD *)v6 + 43) );
  if ( VolumeContext >= 0 )
  {
    v10 = FltFsControlFile(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), 0x90020u, 0, 0, 0, 0, 0);
    *(_DWORD *)(a1 + 24) = v10;
    if ( v10 >= 0 )
    {
      v11 = *(_QWORD *)(*(_QWORD *)(a2 + 32) + 16LL);
      if ( !v11 || (*(_DWORD *)(*(_QWORD *)(v11 + 16) + 48LL) & 0x100) == 0 )
      {
        v12 = 0;
        do
        {
          v13 = 424LL * v12;
          if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v13) )
          {
            v14 = *(void (__fastcall **)(char *))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v13 + 128);
            if ( v14 )
              v14(&v6[*(unsigned int *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v13 + 20)]);
          }
          ++v12;
        }
        while ( v12 <= *((_DWORD *)v6 + 43) );
        *((_DWORD *)v6 + 43) = 0;
      }
    }
    FltReleaseContext(v6);
  }
  else
  {
    FltReleaseContext(v6);
    *(_DWORD *)(a1 + 24) = VolumeContext;
  }
  return 4;
}

```

## disassembly

```asm
0x1400229e4  mov     rax, rsp
0x1400229e7  mov     [rax+18h], r8
0x1400229eb  push    rbx
0x1400229ec  push    rbp
0x1400229ed  push    rsi
0x1400229ee  push    rdi
0x1400229ef  push    r12
0x1400229f1  push    r14
0x1400229f3  sub     rsp, 48h
0x1400229f7  mov     rbp, rdx
0x1400229fa  mov     qword ptr [rax+18h], 0
0x140022a02  mov     r14, rcx
0x140022a05  lea     rdx, [rax+18h]
0x140022a09  mov     rcx, [rbp+18h]; Instance
0x140022a0d  call    WofGetVolumeContext
0x140022a12  mov     esi, eax
0x140022a14  test    eax, eax
0x140022a16  jns     short loc_140022A22
0x140022a18  mov     eax, 1
0x140022a1d  jmp     loc_140022B3E
0x140022a22  mov     rbx, [rsp+78h+Context]
0x140022a2a  lea     r12, WPP_MAIN_CB.Queue+10h
0x140022a31  xor     edi, edi
0x140022a33  mov     eax, edi
0x140022a35  imul    rcx, rax, 1A8h
0x140022a3c  cmp     byte ptr [rcx+r12], 0
0x140022a41  jz      short loc_140022A63
0x140022a43  mov     rax, [rcx+r12+118h]
0x140022a4b  test    rax, rax
0x140022a4e  jz      short loc_140022A63
0x140022a50  mov     ecx, [rcx+r12+14h]
0x140022a55  add     rcx, rbx
0x140022a58  call    _guard_dispatch_icall
0x140022a5d  mov     esi, eax
0x140022a5f  test    eax, eax
0x140022a61  js      short loc_140022A6D
0x140022a63  inc     edi
0x140022a65  cmp     edi, [rbx+0ACh]
0x140022a6b  jbe     short loc_140022A33
0x140022a6d  test    esi, esi
0x140022a6f  jns     short loc_140022A89
0x140022a71  mov     rcx, rbx; Context
0x140022a74  call    cs:__imp_FltReleaseContext
0x140022a7b  nop     dword ptr [rax+rax+00h]
0x140022a80  mov     [r14+18h], esi
0x140022a84  jmp     loc_140022B39
0x140022a89  mov     rdx, [rbp+20h]; FileObject
0x140022a8d  xor     r9d, r9d; InputBuffer
0x140022a90  mov     rcx, [rbp+18h]; Instance
0x140022a94  mov     r8d, 90020h; FsControlCode
0x140022a9a  mov     [rsp+78h+LengthReturned], 0; LengthReturned
0x140022aa3  mov     [rsp+78h+OutputBufferLength], 0; OutputBufferLength
0x140022aab  mov     [rsp+78h+OutputBuffer], 0; OutputBuffer
0x140022ab4  mov     [rsp+78h+InputBufferLength], 0; InputBufferLength
0x140022abc  call    cs:__imp_FltFsControlFile
0x140022ac3  nop     dword ptr [rax+rax+00h]
0x140022ac8  mov     [r14+18h], eax
0x140022acc  test    eax, eax
0x140022ace  js      short loc_140022B2A
0x140022ad0  mov     rax, [rbp+20h]
0x140022ad4  mov     rax, [rax+10h]
0x140022ad8  test    rax, rax
0x140022adb  jz      short loc_140022AEA
0x140022add  mov     rax, [rax+10h]
0x140022ae1  test    dword ptr [rax+30h], 100h
0x140022ae8  jnz     short loc_140022B2A
0x140022aea  xor     edi, edi
0x140022aec  mov     eax, edi
0x140022aee  imul    rcx, rax, 1A8h
0x140022af5  cmp     byte ptr [rcx+r12], 0
0x140022afa  jz      short loc_140022B16
0x140022afc  mov     rax, [rcx+r12+80h]
0x140022b04  test    rax, rax
0x140022b07  jz      short loc_140022B16
0x140022b09  mov     ecx, [rcx+r12+14h]
0x140022b0e  add     rcx, rbx
0x140022b11  call    _guard_dispatch_icall
0x140022b16  inc     edi
0x140022b18  cmp     edi, [rbx+0ACh]
0x140022b1e  jbe     short loc_140022AEC
0x140022b20  mov     dword ptr [rbx+0ACh], 0
0x140022b2a  mov     rcx, rbx; Context
0x140022b2d  call    cs:__imp_FltReleaseContext
0x140022b34  nop     dword ptr [rax+rax+00h]
0x140022b39  mov     eax, 4
0x140022b3e  add     rsp, 48h
0x140022b42  pop     r14
0x140022b44  pop     r12
0x140022b46  pop     rdi
0x140022b47  pop     rsi
0x140022b48  pop     rbp
0x140022b49  pop     rbx
0x140022b4a  retn
```
