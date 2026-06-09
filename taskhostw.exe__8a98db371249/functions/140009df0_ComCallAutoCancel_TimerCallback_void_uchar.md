# ComCallAutoCancel::TimerCallback(void *,uchar)

- ea: `0x140009df0`
- end: `0x140009e35`
- name: `?TimerCallback@ComCallAutoCancel@@CAXPEAXE@Z`
- size: `69`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140009df0`
- `0x140009e3c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCancelCall` at `0x140009dfc`
- `api-ms-win-core-com-l1-1-0!CoCancelCall` at `0x140009dfc`

## pseudocode

```c
void __fastcall ComCallAutoCancel::TimerCallback(_DWORD *a1)
{
  HRESULT v1; // eax
  __int64 v2; // r8

  v1 = CoCancelCall(a1[2], 1u);
  if ( v1 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v2, (unsigned int)v1);
}

```

## disassembly

```asm
0x140009df0  sub     rsp, 28h
0x140009df4  mov     ecx, [rcx+8]; dwThreadId
0x140009df7  mov     edx, 1; ulTimeout
0x140009dfc  call    cs:__imp_CoCancelCall
0x140009e02  test    eax, eax
0x140009e04  jns     short loc_140009E30
0x140009e06  mov     rcx, cs:WPP_GLOBAL_Control
0x140009e0d  lea     rdx, WPP_GLOBAL_Control
0x140009e14  cmp     rcx, rdx
0x140009e17  jz      short loc_140009E30
0x140009e19  test    byte ptr [rcx+1Ch], 1
0x140009e1d  jz      short loc_140009E30
0x140009e1f  mov     rcx, [rcx+10h]
0x140009e23  mov     edx, 0Ch
0x140009e28  mov     r9d, eax
0x140009e2b  call    WPP_SF_D
0x140009e30  add     rsp, 28h
0x140009e34  retn
```
