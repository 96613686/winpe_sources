# WimCbRemoveOverlay

- ea: `0x1400273c0`
- end: `0x14002749f`
- name: `WimCbRemoveOverlay`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x14000c3bc`
- `0x14000d250`
- `0x14000fd74`
- `0x140022cf4`
- `0x1400273c0`
- `0x14002b77c`
- `0x14003c3fc`

## pseudocode

```c
__int64 __fastcall WimCbRemoveOverlay(__int64 a1, __int64 *a2, unsigned int a3)
{
  int v6; // esi
  __int64 v7; // r8
  int v8; // edi
  __int64 v9; // r8
  __int64 v10; // [rsp+38h] [rbp+10h] BYREF

  v10 = 0;
  if ( a3 < 8 )
    return 3221225485LL;
  WimFSFAcquireConfigLock(a1);
  v6 = WimRemoveOverlay(a1 - (unsigned int)dword_14001A2FC, *a2);
  WimFSFReleaseConfigLock(a1);
  if ( v6 >= 0 )
  {
    v8 = WimFSFFindOverlayByDataSource(a1, *a2, &v10);
    if ( v8 >= 0 )
    {
      WimFSFDismountOverlay(v10, 2, v9);
    }
    else if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 17, v9, *a2);
    }
    return (unsigned int)v8;
  }
  else
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 16, v7, *a2);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x1400273c0  mov     [rsp+arg_0], rbx
0x1400273c5  mov     [rsp+arg_10], rsi
0x1400273ca  push    rdi
0x1400273cb  sub     rsp, 20h
0x1400273cf  mov     [rsp+28h+arg_8], 0
0x1400273d8  mov     rbx, rdx
0x1400273db  mov     rdi, rcx
0x1400273de  cmp     r8d, 8
0x1400273e2  jnb     short loc_1400273EE
0x1400273e4  mov     eax, 0C000000Dh
0x1400273e9  jmp     loc_14002748E
0x1400273ee  call    WimFSFAcquireConfigLock
0x1400273f3  mov     eax, cs:dword_14001A2FC
0x1400273f9  mov     rcx, rdi
0x1400273fc  mov     rdx, [rbx]
0x1400273ff  sub     rcx, rax
0x140027402  call    WimRemoveOverlay
0x140027407  mov     rcx, rdi
0x14002740a  mov     esi, eax
0x14002740c  call    WimFSFReleaseConfigLock
0x140027411  test    esi, esi
0x140027413  jns     short loc_14002743F
0x140027415  mov     rcx, cs:WPP_GLOBAL_Control
0x14002741c  mov     edx, [rcx+2Ch]
0x14002741f  test    dl, 8
0x140027422  jz      short loc_14002743B
0x140027424  cmp     byte ptr [rcx+29h], 2
0x140027428  jb      short loc_14002743B
0x14002742a  mov     r9, [rbx]
0x14002742d  mov     edx, 10h
0x140027432  mov     rcx, [rcx+18h]
0x140027436  call    WPP_SF_i
0x14002743b  mov     eax, esi
0x14002743d  jmp     short loc_14002748E
0x14002743f  mov     rdx, [rbx]
0x140027442  lea     r8, [rsp+28h+arg_8]
0x140027447  mov     rcx, rdi
0x14002744a  call    WimFSFFindOverlayByDataSource
0x14002744f  mov     edi, eax
0x140027451  test    eax, eax
0x140027453  jns     short loc_14002747D
0x140027455  mov     rcx, cs:WPP_GLOBAL_Control
0x14002745c  mov     edx, [rcx+2Ch]
0x14002745f  test    dl, 8
0x140027462  jz      short loc_14002748C
0x140027464  cmp     byte ptr [rcx+29h], 2
0x140027468  jb      short loc_14002748C
0x14002746a  mov     r9, [rbx]
0x14002746d  mov     edx, 11h
0x140027472  mov     rcx, [rcx+18h]
0x140027476  call    WPP_SF_i
0x14002747b  jmp     short loc_14002748C
0x14002747d  mov     rcx, [rsp+28h+arg_8]
0x140027482  mov     edx, 2
0x140027487  call    WimFSFDismountOverlay
0x14002748c  mov     eax, edi
0x14002748e  mov     rbx, [rsp+28h+arg_0]
0x140027493  mov     rsi, [rsp+28h+arg_10]
0x140027498  add     rsp, 20h
0x14002749c  pop     rdi
0x14002749d  retn
```
