# ClientDestroyOnDemandContext(void *)

- ea: `0x18000c8e0`
- end: `0x18000c994`
- name: `?ClientDestroyOnDemandContext@@YAXPEAX@Z`
- size: `180`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180012670`
- `0x180012b10`

## callees

- `0x180004450`
- `0x1800044b0`
- `0x1800054c0`
- `0x18000c8e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c938`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c938`

## pseudocode

```c
void __fastcall ClientDestroyOnDemandContext(char *lpMem)
{
  WcmPolicyManager *v2; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      89,
      &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      "ClientDestroyOnDemandContext");
    v2 = WPP_GLOBAL_Control;
  }
  if ( lpMem )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(lpMem + 16));
    WcmFreeMemory(lpMem);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 5u && (*((_BYTE *)v2 + 28) & 1) != 0 )
    WPP_SF_sL(
      *((_QWORD *)v2 + 2),
      90,
      (unsigned int)&WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      (unsigned int)"ClientDestroyOnDemandContext",
      0);
}

```

## disassembly

```asm
0x18000c8e0  mov     [rsp+arg_0], rbx
0x18000c8e5  push    rdi
0x18000c8e6  sub     rsp, 30h
0x18000c8ea  mov     rbx, rcx
0x18000c8ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c8f4  lea     rdi, WPP_GLOBAL_Control
0x18000c8fb  cmp     rcx, rdi
0x18000c8fe  jz      short loc_18000C92F
0x18000c900  cmp     byte ptr [rcx+19h], 5
0x18000c904  jb      short loc_18000C92F
0x18000c906  test    byte ptr [rcx+1Ch], 1
0x18000c90a  jz      short loc_18000C92F
0x18000c90c  mov     rcx, [rcx+10h]
0x18000c910  lea     r9, aClientdestroyo; "ClientDestroyOnDemandContext"
0x18000c917  mov     edx, 59h ; 'Y'
0x18000c91c  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x18000c923  call    WPP_SF_s
0x18000c928  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c92f  test    rbx, rbx
0x18000c932  jz      short loc_18000C953
0x18000c934  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000c938  call    cs:__imp_DeleteCriticalSection
0x18000c93f  nop     dword ptr [rax+rax+00h]
0x18000c944  mov     rcx, rbx; lpMem
0x18000c947  call    WcmFreeMemory
0x18000c94c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c953  cmp     rcx, rdi
0x18000c956  jz      short loc_18000C988
0x18000c958  cmp     byte ptr [rcx+19h], 5
0x18000c95c  jb      short loc_18000C988
0x18000c95e  test    byte ptr [rcx+1Ch], 1
0x18000c962  jz      short loc_18000C988
0x18000c964  mov     rcx, [rcx+10h]
0x18000c968  lea     r9, aClientdestroyo; "ClientDestroyOnDemandContext"
0x18000c96f  mov     edx, 5Ah ; 'Z'
0x18000c974  mov     [rsp+38h+var_18], 0
0x18000c97c  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x18000c983  call    WPP_SF_sL
0x18000c988  mov     rbx, [rsp+38h+arg_0]
0x18000c98d  add     rsp, 30h
0x18000c991  pop     rdi
0x18000c992  retn
```
