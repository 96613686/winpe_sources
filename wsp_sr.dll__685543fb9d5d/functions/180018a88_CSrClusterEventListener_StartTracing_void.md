# CSrClusterEventListener::StartTracing(void)

- ea: `0x180018a88`
- end: `0x180018c12`
- name: `?StartTracing@CSrClusterEventListener@@QEAAKXZ`
- size: `394`
- prototype: `unsigned int __fastcall(CSrClusterEventListener *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180018440`

## callees

- `0x1800014e0`
- `0x1800067cc`
- `0x1800067fc`
- `0x180018534`
- `0x180018a88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018aeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018aeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b42`
- `CLUSAPI!CloseClusterNotifyPort` at `0x180018bab`
- `CLUSAPI!CloseClusterNotifyPort` at `0x180018bab`
- `CLUSAPI!RegisterClusterResourceTypeNotifyV2` at `0x180018b70`
- `CLUSAPI!RegisterClusterResourceTypeNotifyV2` at `0x180018b70`
- `CLUSAPI!OpenCluster` at `0x180018ad7`
- `CLUSAPI!OpenCluster` at `0x180018ad7`
- `CLUSAPI!CreateClusterNotifyPortV2` at `0x180018b2e`
- `CLUSAPI!CreateClusterNotifyPortV2` at `0x180018b2e`
- `CLUSAPI!CloseCluster` at `0x180018bbf`
- `CLUSAPI!CloseCluster` at `0x180018bbf`

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
0x180018a88  push    rbx
0x180018a8a  push    rbp
0x180018a8b  push    rsi
0x180018a8c  push    rdi
0x180018a8d  push    r12
0x180018a8f  push    r14
0x180018a91  sub     rsp, 58h
0x180018a95  mov     rax, cs:__security_cookie
0x180018a9c  xor     rax, rsp
0x180018a9f  mov     [rsp+88h+var_48], rax
0x180018aa4  mov     r14, rcx
0x180018aa7  mov     rcx, cs:WPP_GLOBAL_Control
0x180018aae  lea     r12, WPP_GLOBAL_Control
0x180018ab5  cmp     rcx, r12
0x180018ab8  jz      short loc_180018AD5
0x180018aba  test    byte ptr [rcx+1Ch], 4
0x180018abe  jz      short loc_180018AD5
0x180018ac0  mov     rcx, [rcx+10h]
0x180018ac4  lea     r8, WPP_2842f3940e023d3d9a1de50e7181de48_Traceguids
0x180018acb  mov     edx, 16h
0x180018ad0  call    WPP_SF_
0x180018ad5  xor     ecx, ecx; lpszClusterName
0x180018ad7  call    cs:__imp_OpenCluster
0x180018ade  nop     dword ptr [rax+rax+00h]
0x180018ae3  mov     rdi, rax
0x180018ae6  test    rax, rax
0x180018ae9  jnz     short loc_180018B01
0x180018aeb  call    cs:__imp_GetLastError
0x180018af2  nop     dword ptr [rax+rax+00h]
0x180018af7  mov     ebx, eax
0x180018af9  test    eax, eax
0x180018afb  jnz     loc_180018BCB
0x180018b01  mov     r9d, 1
0x180018b07  mov     [rsp+88h+var_58], 1
0x180018b10  lea     r8, [rsp+88h+var_58]
0x180018b15  mov     [rsp+88h+var_50], 203h
0x180018b1e  mov     rdx, rdi
0x180018b21  mov     [rsp+88h+dwNotifyKey], 0
0x180018b2a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180018b2e  call    cs:__imp_CreateClusterNotifyPortV2
0x180018b35  nop     dword ptr [rax+rax+00h]
0x180018b3a  mov     rsi, rax
0x180018b3d  test    rax, rax
0x180018b40  jnz     short loc_180018B54
0x180018b42  call    cs:__imp_GetLastError
0x180018b49  nop     dword ptr [rax+rax+00h]
0x180018b4e  mov     ebx, eax
0x180018b50  test    eax, eax
0x180018b52  jnz     short loc_180018BB7
0x180018b54  lea     r9, resTypeName; "Storage Replica"
0x180018b5b  mov     [rsp+88h+dwNotifyKey], 0; dwNotifyKey
0x180018b64  mov     r8d, 20h ; ' '; Flags
0x180018b6a  mov     rdx, rdi; hCluster
0x180018b6d  mov     rcx, rsi; hChange
0x180018b70  call    cs:__imp_RegisterClusterResourceTypeNotifyV2
0x180018b77  nop     dword ptr [rax+rax+00h]
0x180018b7c  mov     ebx, eax
0x180018b7e  test    eax, eax
0x180018b80  jnz     short loc_180018BA3
0x180018b82  mov     bpl, 1
0x180018b85  mov     rdx, r14
0x180018b88  mov     rcx, rsi
0x180018b8b  call    SrEventListenerpProcessNextClusterEvent
0x180018b90  mov     ebx, eax
0x180018b92  test    eax, eax
0x180018b94  jnz     short loc_180018BA3
0x180018b96  mov     al, [r14+1Ch]
0x180018b9a  neg     al
0x180018b9c  sbb     cl, cl
0x180018b9e  and     bpl, cl
0x180018ba1  jnz     short loc_180018B85
0x180018ba3  test    rsi, rsi
0x180018ba6  jz      short loc_180018BB7
0x180018ba8  mov     rcx, rsi; hChange
0x180018bab  call    cs:__imp_CloseClusterNotifyPort
0x180018bb2  nop     dword ptr [rax+rax+00h]
0x180018bb7  test    rdi, rdi
0x180018bba  jz      short loc_180018BCB
0x180018bbc  mov     rcx, rdi; hCluster
0x180018bbf  call    cs:__imp_CloseCluster
0x180018bc6  nop     dword ptr [rax+rax+00h]
0x180018bcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180018bd2  cmp     rcx, r12
0x180018bd5  jz      short loc_180018BF5
0x180018bd7  test    byte ptr [rcx+1Ch], 1
0x180018bdb  jz      short loc_180018BF5
0x180018bdd  mov     rcx, [rcx+10h]
0x180018be1  lea     r8, WPP_2842f3940e023d3d9a1de50e7181de48_Traceguids
0x180018be8  mov     edx, 17h
0x180018bed  mov     r9d, ebx
0x180018bf0  call    WPP_SF_d
0x180018bf5  mov     eax, ebx
0x180018bf7  mov     rcx, [rsp+88h+var_48]
0x180018bfc  xor     rcx, rsp; StackCookie
0x180018bff  call    __security_check_cookie
0x180018c04  add     rsp, 58h
0x180018c08  pop     r14
0x180018c0a  pop     r12
0x180018c0c  pop     rdi
0x180018c0d  pop     rsi
0x180018c0e  pop     rbp
0x180018c0f  pop     rbx
0x180018c10  retn
```
