# WofPrePnpSurpriseRemove

- ea: `0x14002511c`
- end: `0x1400251e8`
- name: `WofPrePnpSurpriseRemove`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14003d460`

## callees

- `0x1400014d0`
- `0x140011640`
- `0x14002511c`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x1400251aa`
- `FLTMGR!FltReleaseContext` at `0x1400251c3`
- `FLTMGR!FltReleaseContext` at `0x1400251aa`
- `FLTMGR!FltReleaseContext` at `0x1400251c3`

## pseudocode

```c
__int64 __fastcall WofPrePnpSurpriseRemove(__int64 a1, __int64 a2)
{
  int VolumeContext; // esi
  __int64 result; // rax
  char *v5; // rbx
  unsigned int v6; // edi
  __int64 v7; // rcx
  __int64 (__fastcall *v8)(char *); // rax
  int v9; // esi
  PFLT_CONTEXT Context; // [rsp+50h] [rbp+18h] BYREF

  Context = 0;
  VolumeContext = WofGetVolumeContext(*(PFLT_INSTANCE *)(a2 + 24), &Context);
  if ( VolumeContext < 0 )
    return 1;
  v5 = (char *)Context;
  v6 = 0;
  do
  {
    v7 = 424LL * v6;
    if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v7) )
    {
      v8 = *(__int64 (__fastcall **)(char *))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v7 + 280);
      if ( v8 )
      {
        v9 = v8(&v5[*(unsigned int *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v7 + 20)]);
        if ( v9 < 0 )
        {
          FltReleaseContext(v5);
          result = 4;
          *(_DWORD *)(a1 + 24) = v9;
          return result;
        }
      }
    }
    ++v6;
  }
  while ( v6 <= *((_DWORD *)v5 + 43) );
  FltReleaseContext(v5);
  return 5;
}

```

## disassembly

```asm
0x14002511c  mov     r11, rsp
0x14002511f  mov     [r11+8], rbx
0x140025123  mov     [r11+10h], rbp
0x140025127  mov     [r11+18h], r8
0x14002512b  push    rsi
0x14002512c  push    rdi
0x14002512d  push    r14
0x14002512f  sub     rsp, 20h
0x140025133  mov     rax, rdx
0x140025136  mov     qword ptr [r11+18h], 0
0x14002513e  mov     rbp, rcx
0x140025141  lea     rdx, [r11+18h]
0x140025145  mov     rcx, [rax+18h]; Instance
0x140025149  call    WofGetVolumeContext
0x14002514e  mov     esi, eax
0x140025150  test    eax, eax
0x140025152  jns     short loc_14002515B
0x140025154  mov     eax, 1
0x140025159  jmp     short loc_1400251D4
0x14002515b  mov     rbx, [rsp+38h+Context]
0x140025160  lea     r14, WPP_MAIN_CB.Queue+10h
0x140025167  xor     edi, edi
0x140025169  mov     eax, edi
0x14002516b  imul    rcx, rax, 1A8h
0x140025172  cmp     byte ptr [rcx+r14], 0
0x140025177  jz      short loc_140025199
0x140025179  mov     rax, [rcx+r14+118h]
0x140025181  test    rax, rax
0x140025184  jz      short loc_140025199
0x140025186  mov     ecx, [rcx+r14+14h]
0x14002518b  add     rcx, rbx
0x14002518e  call    _guard_dispatch_icall
0x140025193  mov     esi, eax
0x140025195  test    eax, eax
0x140025197  js      short loc_1400251A7
0x140025199  inc     edi
0x14002519b  cmp     edi, [rbx+0ACh]
0x1400251a1  jbe     short loc_140025169
0x1400251a3  test    esi, esi
0x1400251a5  jns     short loc_1400251C0
0x1400251a7  mov     rcx, rbx; Context
0x1400251aa  call    cs:__imp_FltReleaseContext
0x1400251b1  nop     dword ptr [rax+rax+00h]
0x1400251b6  mov     eax, 4
0x1400251bb  mov     [rbp+18h], esi
0x1400251be  jmp     short loc_1400251D4
0x1400251c0  mov     rcx, rbx; Context
0x1400251c3  call    cs:__imp_FltReleaseContext
0x1400251ca  nop     dword ptr [rax+rax+00h]
0x1400251cf  mov     eax, 5
0x1400251d4  mov     rbx, [rsp+38h+arg_0]
0x1400251d9  mov     rbp, [rsp+38h+arg_8]
0x1400251de  add     rsp, 20h
0x1400251e2  pop     r14
0x1400251e4  pop     rdi
0x1400251e5  pop     rsi
0x1400251e6  retn
```
