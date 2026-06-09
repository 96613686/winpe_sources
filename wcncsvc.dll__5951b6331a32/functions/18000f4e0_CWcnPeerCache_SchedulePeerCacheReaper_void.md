# CWcnPeerCache::SchedulePeerCacheReaper(void)

- ea: `0x18000f4e0`
- end: `0x18000f5dc`
- name: `?SchedulePeerCacheReaper@CWcnPeerCache@@QEAAXXZ`
- size: `252`
- prototype: `void __fastcall(CWcnPeerCache *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e714`

## callees

- `0x180004fb8`
- `0x180005014`
- `0x18000f4e0`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f55a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f55a`

## pseudocode

```c
void __fastcall CWcnPeerCache::SchedulePeerCacheReaper(CWcnPeerCache *this)
{
  _BYTE *v2; // r10
  const char *Indent; // rax
  __int64 v4; // r10
  struct _TP_TIMER *v5; // rcx
  unsigned int v6; // eax
  __int64 v7; // r10
  const char *v8; // rax
  __int64 v9; // r10
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

  pftDueTime = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v4 + 16), 89, WPP_f34e634574083547aa3a426270948a29_Traceguids, Indent);
    v2 = WPP_GLOBAL_Control;
  }
  if ( !*((_BYTE *)this + 120) )
  {
    v5 = (struct _TP_TIMER *)*((_QWORD *)this + 14);
    pftDueTime = (struct _FILETIME)-100000000LL;
    SetThreadpoolTimer(v5, &pftDueTime, 0x2710u, 0x2710u);
    *((_BYTE *)this + 120) = 1;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v6 = (unsigned int)GetIndent(0);
      WPP_SF_sd(*(_QWORD *)(v7 + 16), 90, (unsigned int)WPP_f34e634574083547aa3a426270948a29_Traceguids, v6, 16);
      v2 = WPP_GLOBAL_Control;
    }
  }
  if ( v2 != (_BYTE *)&WPP_GLOBAL_Control && v2[25] >= 6u )
  {
    v8 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v9 + 16), 91, WPP_f34e634574083547aa3a426270948a29_Traceguids, v8);
  }
}

```

## disassembly

```asm
0x18000f4e0  mov     [rsp+arg_8], rbx
0x18000f4e5  push    rdi
0x18000f4e6  sub     rsp, 30h
0x18000f4ea  mov     rbx, rcx
0x18000f4ed  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], 0
0x18000f4f6  mov     r10, cs:WPP_GLOBAL_Control
0x18000f4fd  lea     rdi, WPP_GLOBAL_Control
0x18000f504  cmp     r10, rdi
0x18000f507  jz      short loc_18000F539
0x18000f509  cmp     byte ptr [r10+19h], 6
0x18000f50e  jb      short loc_18000F539
0x18000f510  mov     ecx, 1; int
0x18000f515  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000f51a  mov     rcx, [r10+10h]
0x18000f51e  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000f525  mov     edx, 59h ; 'Y'
0x18000f52a  mov     r9, rax
0x18000f52d  call    WPP_SF_s
0x18000f532  mov     r10, cs:WPP_GLOBAL_Control
0x18000f539  cmp     byte ptr [rbx+78h], 0
0x18000f53d  jnz     short loc_18000F5A5
0x18000f53f  mov     rcx, [rbx+70h]; pti
0x18000f543  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000f548  mov     r9d, 2710h; msWindowLength
0x18000f54e  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], 0FFFFFFFFFA0A1F00h
0x18000f557  mov     r8d, r9d; msPeriod
0x18000f55a  call    cs:__imp_SetThreadpoolTimer
0x18000f560  mov     byte ptr [rbx+78h], 1
0x18000f564  mov     r10, cs:WPP_GLOBAL_Control
0x18000f56b  cmp     r10, rdi
0x18000f56e  jz      short loc_18000F5D1
0x18000f570  cmp     byte ptr [r10+19h], 4
0x18000f575  jb      short loc_18000F5A5
0x18000f577  xor     ecx, ecx; int
0x18000f579  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000f57e  mov     rcx, [r10+10h]
0x18000f582  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000f589  mov     edx, 5Ah ; 'Z'
0x18000f58e  mov     [rsp+38h+var_18], 2710h
0x18000f596  mov     r9, rax
0x18000f599  call    WPP_SF_sd
0x18000f59e  mov     r10, cs:WPP_GLOBAL_Control
0x18000f5a5  cmp     r10, rdi
0x18000f5a8  jz      short loc_18000F5D1
0x18000f5aa  cmp     byte ptr [r10+19h], 6
0x18000f5af  jb      short loc_18000F5D1
0x18000f5b1  or      ecx, 0FFFFFFFFh; int
0x18000f5b4  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000f5b9  mov     rcx, [r10+10h]
0x18000f5bd  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000f5c4  mov     edx, 5Bh ; '['
0x18000f5c9  mov     r9, rax
0x18000f5cc  call    WPP_SF_s
0x18000f5d1  mov     rbx, [rsp+38h+arg_8]
0x18000f5d6  add     rsp, 30h
0x18000f5da  pop     rdi
0x18000f5db  retn
```
