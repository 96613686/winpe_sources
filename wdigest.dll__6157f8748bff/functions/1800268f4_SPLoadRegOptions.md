# SPLoadRegOptions

- ea: `0x1800268f4`
- end: `0x18002695d`
- name: `SPLoadRegOptions`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180026ad0`
- `0x180031510`

## callees

- `0x180010150`
- `0x180011fec`
- `0x1800268f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002693c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002693c`

## pseudocode

```c
__int64 SPLoadRegOptions()
{
  if ( g_hParamEvent )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids);
  }
  else
  {
    g_hParamEvent = CreateEventW(0, 0, 0, 0);
    DigestWatchParamKey(g_hParamEvent, 0);
  }
  return 1;
}

```

## disassembly

```asm
0x1800268f4  sub     rsp, 28h
0x1800268f8  cmp     cs:?g_hParamEvent@@3PEAXEA, 0; void * g_hParamEvent
0x180026900  jz      short loc_180026932
0x180026902  mov     rcx, cs:WPP_GLOBAL_Control
0x180026909  lea     rax, WPP_GLOBAL_Control
0x180026910  cmp     rcx, rax
0x180026913  jz      short loc_180026953
0x180026915  test    byte ptr [rcx+1Ch], 4
0x180026919  jz      short loc_180026953
0x18002691b  mov     rcx, [rcx+10h]
0x18002691f  lea     r8, WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids
0x180026926  mov     edx, 27h ; '''
0x18002692b  call    WPP_SF_
0x180026930  jmp     short loc_180026953
0x180026932  xor     r9d, r9d; lpName
0x180026935  xor     r8d, r8d; bInitialState
0x180026938  xor     edx, edx; bManualReset
0x18002693a  xor     ecx, ecx; lpEventAttributes
0x18002693c  call    cs:__imp_CreateEventW
0x180026942  mov     rcx, rax; PVOID
0x180026945  mov     cs:?g_hParamEvent@@3PEAXEA, rax; void * g_hParamEvent
0x18002694c  xor     edx, edx; BOOLEAN
0x18002694e  call    DigestWatchParamKey
0x180026953  mov     eax, 1
0x180026958  add     rsp, 28h
0x18002695c  retn
```
