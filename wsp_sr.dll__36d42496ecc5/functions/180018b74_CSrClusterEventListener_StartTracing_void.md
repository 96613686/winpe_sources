# CSrClusterEventListener::StartTracing(void)

- ea: `0x180018b74`
- end: `0x180018cd3`
- name: `?StartTracing@CSrClusterEventListener@@QEAAKXZ`
- size: `351`
- prototype: `__int64 __fastcall(CSrClusterEventListener *this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180018590`

## callees

- `0x1800014e0`
- `0x180006778`
- `0x1800067a0`
- `0x180018670`
- `0x180018b74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c1c`
- `CLUSAPI!CloseClusterNotifyPort` at `0x180018c79`
- `CLUSAPI!CloseClusterNotifyPort` at `0x180018c79`
- `CLUSAPI!RegisterClusterResourceTypeNotifyV2` at `0x180018c44`
- `CLUSAPI!RegisterClusterResourceTypeNotifyV2` at `0x180018c44`
- `CLUSAPI!OpenCluster` at `0x180018bc3`
- `CLUSAPI!OpenCluster` at `0x180018bc3`
- `CLUSAPI!CreateClusterNotifyPortV2` at `0x180018c0e`
- `CLUSAPI!CreateClusterNotifyPortV2` at `0x180018c0e`
- `CLUSAPI!CloseCluster` at `0x180018c87`
- `CLUSAPI!CloseCluster` at `0x180018c87`

## pseudocode

```c
__int64 __fastcall CSrClusterEventListener::StartTracing(CSrClusterEventListener *this)
{
  struct _HCLUSTER *v2; // rdi
  DWORD ClusterEvent; // ebx
  struct _HCHANGE *ClusterNotifyPortV2; // rsi
  char v5; // bp
  _QWORD v7[2]; // [rsp+30h] [rbp-58h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_2842f3940e023d3d9a1de50e7181de48_Traceguids);
  v2 = OpenCluster(0);
  if ( v2 || (ClusterEvent = GetLastError()) == 0 )
  {
    v7[0] = 1;
    v7[1] = 515;
    ClusterNotifyPortV2 = (struct _HCHANGE *)CreateClusterNotifyPortV2(-1, v2, v7, 1, 0);
    if ( ClusterNotifyPortV2 || (ClusterEvent = GetLastError()) == 0 )
    {
      ClusterEvent = RegisterClusterResourceTypeNotifyV2(ClusterNotifyPortV2, v2, 32, L"Storage Replica", 0);
      if ( !ClusterEvent )
      {
        v5 = 1;
        do
        {
          ClusterEvent = SrEventListenerpProcessNextClusterEvent(ClusterNotifyPortV2, this);
          if ( ClusterEvent )
            break;
          v5 = *((_BYTE *)this + 28) != 0 ? v5 : 0;
        }
        while ( v5 );
      }
      if ( ClusterNotifyPortV2 )
        CloseClusterNotifyPort(ClusterNotifyPortV2);
    }
    if ( v2 )
      CloseCluster(v2);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_2842f3940e023d3d9a1de50e7181de48_Traceguids, ClusterEvent);
  return ClusterEvent;
}

```

## disassembly

```asm
0x180018b74  push    rbx
0x180018b76  push    rbp
0x180018b77  push    rsi
0x180018b78  push    rdi
0x180018b79  push    r12
0x180018b7b  push    r14
0x180018b7d  sub     rsp, 58h
0x180018b81  mov     rax, cs:__security_cookie
0x180018b88  xor     rax, rsp
0x180018b8b  mov     [rsp+88h+var_48], rax
0x180018b90  mov     r14, rcx
0x180018b93  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b9a  lea     r12, WPP_GLOBAL_Control
0x180018ba1  cmp     rcx, r12
0x180018ba4  jz      short loc_180018BC1
0x180018ba6  test    byte ptr [rcx+1Ch], 4
0x180018baa  jz      short loc_180018BC1
0x180018bac  mov     rcx, [rcx+10h]
0x180018bb0  lea     r8, WPP_2842f3940e023d3d9a1de50e7181de48_Traceguids
0x180018bb7  mov     edx, 16h
0x180018bbc  call    WPP_SF_
0x180018bc1  xor     ecx, ecx; lpszClusterName
0x180018bc3  call    cs:__imp_OpenCluster
0x180018bc9  mov     rdi, rax
0x180018bcc  test    rax, rax
0x180018bcf  jnz     short loc_180018BE1
0x180018bd1  call    cs:__imp_GetLastError
0x180018bd7  mov     ebx, eax
0x180018bd9  test    eax, eax
0x180018bdb  jnz     loc_180018C8D
0x180018be1  mov     r9d, 1
0x180018be7  mov     [rsp+88h+var_58], 1
0x180018bf0  lea     r8, [rsp+88h+var_58]
0x180018bf5  mov     [rsp+88h+var_50], 203h
0x180018bfe  mov     rdx, rdi
0x180018c01  mov     [rsp+88h+dwNotifyKey], 0
0x180018c0a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180018c0e  call    cs:__imp_CreateClusterNotifyPortV2
0x180018c14  mov     rsi, rax
0x180018c17  test    rax, rax
0x180018c1a  jnz     short loc_180018C28
0x180018c1c  call    cs:__imp_GetLastError
0x180018c22  mov     ebx, eax
0x180018c24  test    eax, eax
0x180018c26  jnz     short loc_180018C7F
0x180018c28  lea     r9, resTypeName; "Storage Replica"
0x180018c2f  mov     [rsp+88h+dwNotifyKey], 0; dwNotifyKey
0x180018c38  mov     r8d, 20h ; ' '; Flags
0x180018c3e  mov     rdx, rdi; hCluster
0x180018c41  mov     rcx, rsi; hChange
0x180018c44  call    cs:__imp_RegisterClusterResourceTypeNotifyV2
0x180018c4a  mov     ebx, eax
0x180018c4c  test    eax, eax
0x180018c4e  jnz     short loc_180018C71
0x180018c50  mov     bpl, 1
0x180018c53  mov     rdx, r14
0x180018c56  mov     rcx, rsi
0x180018c59  call    SrEventListenerpProcessNextClusterEvent
0x180018c5e  mov     ebx, eax
0x180018c60  test    eax, eax
0x180018c62  jnz     short loc_180018C71
0x180018c64  mov     al, [r14+1Ch]
0x180018c68  neg     al
0x180018c6a  sbb     cl, cl
0x180018c6c  and     bpl, cl
0x180018c6f  jnz     short loc_180018C53
0x180018c71  test    rsi, rsi
0x180018c74  jz      short loc_180018C7F
0x180018c76  mov     rcx, rsi; hChange
0x180018c79  call    cs:__imp_CloseClusterNotifyPort
0x180018c7f  test    rdi, rdi
0x180018c82  jz      short loc_180018C8D
0x180018c84  mov     rcx, rdi; hCluster
0x180018c87  call    cs:__imp_CloseCluster
0x180018c8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c94  cmp     rcx, r12
0x180018c97  jz      short loc_180018CB7
0x180018c99  test    byte ptr [rcx+1Ch], 1
0x180018c9d  jz      short loc_180018CB7
0x180018c9f  mov     rcx, [rcx+10h]
0x180018ca3  lea     r8, WPP_2842f3940e023d3d9a1de50e7181de48_Traceguids
0x180018caa  mov     edx, 17h
0x180018caf  mov     r9d, ebx
0x180018cb2  call    WPP_SF_d
0x180018cb7  mov     eax, ebx
0x180018cb9  mov     rcx, [rsp+88h+var_48]
0x180018cbe  xor     rcx, rsp; StackCookie
0x180018cc1  call    __security_check_cookie
0x180018cc6  add     rsp, 58h
0x180018cca  pop     r14
0x180018ccc  pop     r12
0x180018cce  pop     rdi
0x180018ccf  pop     rsi
0x180018cd0  pop     rbp
0x180018cd1  pop     rbx
0x180018cd2  retn
```
