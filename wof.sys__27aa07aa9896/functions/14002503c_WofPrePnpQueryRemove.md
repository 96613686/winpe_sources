# WofPrePnpQueryRemove

- ea: `0x14002503c`
- end: `0x140025115`
- name: `WofPrePnpQueryRemove`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14003d4b0`

## callees

- `0x1400014d0`
- `0x140011640`
- `0x14002503c`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x1400250da`
- `FLTMGR!FltReleaseContext` at `0x1400250f5`
- `FLTMGR!FltReleaseContext` at `0x1400250da`
- `FLTMGR!FltReleaseContext` at `0x1400250f5`

## pseudocode

```c
__int64 __fastcall WofPrePnpQueryRemove(__int64 a1, __int64 a2, __int64 a3)
{
  int VolumeContext; // edi
  __int64 result; // rax
  unsigned int i; // ebx
  __int64 v7; // rcx
  __int64 (__fastcall *v8)(char *, int *); // rax
  char *v9; // rcx
  int v10; // edi
  PFLT_CONTEXT Context; // [rsp+48h] [rbp+10h] BYREF
  int v12; // [rsp+50h] [rbp+18h] BYREF
  int v13; // [rsp+54h] [rbp+1Ch]

  v13 = HIDWORD(a3);
  Context = 0;
  v12 = 0;
  VolumeContext = WofGetVolumeContext(*(PFLT_INSTANCE *)(a2 + 24), &Context);
  if ( VolumeContext < 0 )
    return 1;
  for ( i = 0; i < 4; ++i )
  {
    v7 = 424LL * i;
    if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v7) )
    {
      v8 = *(__int64 (__fastcall **)(char *, int *))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v7 + 296);
      if ( v8 )
      {
        v9 = (char *)Context + *(unsigned int *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v7 + 20);
        v12 = 0;
        v10 = v8(v9, &v12);
        if ( v10 < 0 )
        {
          FltReleaseContext(Context);
          result = 4;
          *(_DWORD *)(a1 + 24) = v10;
          return result;
        }
      }
    }
  }
  FltReleaseContext(Context);
  return 5;
}

```

## disassembly

```asm
0x14002503c  mov     r11, rsp
0x14002503f  mov     [r11+8], rbx
0x140025043  mov     [r11+18h], r8
0x140025047  push    rbp
0x140025048  push    rdi
0x140025049  push    r15
0x14002504b  sub     rsp, 20h
0x14002504f  mov     rax, rdx
0x140025052  mov     qword ptr [r11+10h], 0
0x14002505a  mov     rbp, rcx
0x14002505d  mov     [rsp+38h+arg_10], 0
0x140025065  lea     rdx, [r11+10h]
0x140025069  mov     rcx, [rax+18h]; Instance
0x14002506d  call    WofGetVolumeContext
0x140025072  mov     edi, eax
0x140025074  test    eax, eax
0x140025076  jns     short loc_140025082
0x140025078  mov     eax, 1
0x14002507d  jmp     loc_140025106
0x140025082  xor     ebx, ebx
0x140025084  lea     r15, WPP_MAIN_CB.Queue+10h
0x14002508b  mov     eax, ebx
0x14002508d  imul    rcx, rax, 1A8h
0x140025094  cmp     byte ptr [rcx+r15], 0
0x140025099  jz      short loc_1400250CA
0x14002509b  mov     rax, [rcx+r15+128h]
0x1400250a3  test    rax, rax
0x1400250a6  jz      short loc_1400250CA
0x1400250a8  mov     ecx, [rcx+r15+14h]
0x1400250ad  lea     rdx, [rsp+38h+arg_10]
0x1400250b2  add     rcx, [rsp+38h+Context]
0x1400250b7  mov     [rsp+38h+arg_10], 0
0x1400250bf  call    _guard_dispatch_icall
0x1400250c4  mov     edi, eax
0x1400250c6  test    eax, eax
0x1400250c8  js      short loc_1400250D5
0x1400250ca  inc     ebx
0x1400250cc  cmp     ebx, 4
0x1400250cf  jb      short loc_14002508B
0x1400250d1  test    edi, edi
0x1400250d3  jns     short loc_1400250F0
0x1400250d5  mov     rcx, [rsp+38h+Context]; Context
0x1400250da  call    cs:__imp_FltReleaseContext
0x1400250e1  nop     dword ptr [rax+rax+00h]
0x1400250e6  mov     eax, 4
0x1400250eb  mov     [rbp+18h], edi
0x1400250ee  jmp     short loc_140025106
0x1400250f0  mov     rcx, [rsp+38h+Context]; Context
0x1400250f5  call    cs:__imp_FltReleaseContext
0x1400250fc  nop     dword ptr [rax+rax+00h]
0x140025101  mov     eax, 5
0x140025106  mov     rbx, [rsp+38h+arg_0]
0x14002510b  add     rsp, 20h
0x14002510f  pop     r15
0x140025111  pop     rdi
0x140025112  pop     rbp
0x140025113  retn
```
