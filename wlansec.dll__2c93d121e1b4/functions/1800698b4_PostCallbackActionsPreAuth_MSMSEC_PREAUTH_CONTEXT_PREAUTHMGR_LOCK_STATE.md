# PostCallbackActionsPreAuth(MSMSEC_PREAUTH_CONTEXT *,_PREAUTHMGR_LOCK_STATE *)

- ea: `0x1800698b4`
- end: `0x1800699ab`
- name: `?PostCallbackActionsPreAuth@@YAKPEAUMSMSEC_PREAUTH_CONTEXT@@PEAU_PREAUTHMGR_LOCK_STATE@@@Z`
- size: `247`
- prototype: `unsigned int __fastcall(struct MSMSEC_PREAUTH_CONTEXT *, struct _PREAUTHMGR_LOCK_STATE *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18006a0f0`
- `0x18006a310`
- `0x18006a6a4`

## callees

- `0x18000892c`
- `0x180008998`
- `0x180013bc0`
- `0x1800169c0`
- `0x1800698b4`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180069931`
- `MobileNetworking!ReleaseWriteLock` at `0x180069931`

## pseudocode

```c
__int64 __fastcall PostCallbackActionsPreAuth(struct MSMSEC_PREAUTH_CONTEXT *a1, struct _PREAUTHMGR_LOCK_STATE *a2)
{
  PVOID *v4; // rcx
  unsigned int *v5; // rbx

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 23, WPP_c3b9857fbeac3feae34c8ad1e975ce4f_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = (unsigned int *)((char *)a1 - 416);
  if ( *(_DWORD *)a2 )
  {
    TraceAdapterId(*v5, "<<< Unlocking <<<");
    ReleaseWriteLock((char *)a1 - 2912, (char *)a1 - 400, "PostCallbackActionsPreAuth", 165);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)a2 + 1) )
  {
    TraceAdapterId(*v5, "<<< Derefing <<<");
    SecMgrDerefAdapterEx((struct MSMSEC_PREAUTH_CONTEXT *)((char *)a1 - 2912), "PostCallbackActionsPreAuth", 169);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x100) != 0 )
    WPP_SF_d(v4[7], 24, WPP_c3b9857fbeac3feae34c8ad1e975ce4f_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x1800698b4  push    rbx
0x1800698b6  push    rsi
0x1800698b7  push    rdi
0x1800698b8  push    r14
0x1800698ba  sub     rsp, 28h
0x1800698be  mov     rsi, rdx
0x1800698c1  mov     rdi, rcx
0x1800698c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800698cb  lea     r14, WPP_GLOBAL_Control
0x1800698d2  cmp     rcx, r14
0x1800698d5  jz      short loc_1800698FC
0x1800698d7  test    dword ptr [rcx+44h], 100h
0x1800698de  jz      short loc_1800698FC
0x1800698e0  mov     rcx, [rcx+38h]
0x1800698e4  lea     r8, WPP_c3b9857fbeac3feae34c8ad1e975ce4f_Traceguids
0x1800698eb  mov     edx, 17h
0x1800698f0  call    WPP_SF_
0x1800698f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800698fc  cmp     dword ptr [rsi], 0
0x1800698ff  lea     rbx, [rdi-1A0h]
0x180069906  jz      short loc_180069944
0x180069908  mov     ecx, [rbx]; unsigned int
0x18006990a  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180069911  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180069916  lea     rdx, [rdi-190h]
0x18006991d  mov     r9d, 0A5h
0x180069923  lea     r8, aPostcallbackac; "PostCallbackActionsPreAuth"
0x18006992a  lea     rcx, [rdi-0B60h]
0x180069931  call    cs:__imp_ReleaseWriteLock
0x180069938  nop     dword ptr [rax+rax+00h]
0x18006993d  mov     rcx, cs:WPP_GLOBAL_Control
0x180069944  cmp     dword ptr [rsi+4], 0
0x180069948  jz      short loc_180069978
0x18006994a  mov     ecx, [rbx]; unsigned int
0x18006994c  lea     rdx, aDerefing; "<<< Derefing <<<"
0x180069953  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180069958  mov     r8d, 0A9h; int
0x18006995e  lea     rdx, aPostcallbackac; "PostCallbackActionsPreAuth"
0x180069965  lea     rcx, [rdi-0B60h]; struct MSMSEC_INTF_CONTEXT *
0x18006996c  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180069971  mov     rcx, cs:WPP_GLOBAL_Control
0x180069978  cmp     rcx, r14
0x18006997b  jz      short loc_18006999E
0x18006997d  test    dword ptr [rcx+44h], 100h
0x180069984  jz      short loc_18006999E
0x180069986  mov     rcx, [rcx+38h]
0x18006998a  lea     r8, WPP_c3b9857fbeac3feae34c8ad1e975ce4f_Traceguids
0x180069991  mov     edx, 18h
0x180069996  xor     r9d, r9d
0x180069999  call    WPP_SF_d
0x18006999e  xor     eax, eax
0x1800699a0  add     rsp, 28h
0x1800699a4  pop     r14
0x1800699a6  pop     rdi
0x1800699a7  pop     rsi
0x1800699a8  pop     rbx
0x1800699a9  retn
```
