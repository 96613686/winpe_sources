# IPNotifications::IPNotificationsCallback(void *,_MIB_UNICASTIPADDRESS_ROW *,_MIB_NOTIFICATION_TYPE)

- ea: `0x180057850`
- end: `0x180057af0`
- name: `?IPNotificationsCallback@IPNotifications@@SAXPEAXPEAU_MIB_UNICASTIPADDRESS_ROW@@W4_MIB_NOTIFICATION_TYPE@@@Z`
- size: `672`
- prototype: `void __fastcall(char *CallerContext, PMIB_UNICASTIPADDRESS_ROW Row, unsigned int NotificationType)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180007794`
- `0x1800077bc`
- `0x18000a3a0`
- `0x180057850`
- `0x18007755e`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180057a8f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180057a8f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800579a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800579a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057996`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057996`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057a52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057a52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057a85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057a85`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall IPNotifications::IPNotificationsCallback(
        char *CallerContext,
        PMIB_UNICASTIPADDRESS_ROW Row,
        unsigned int NotificationType)
{
  PVOID *v6; // rcx
  __int64 v7; // rdx
  HANDLE ProcessHeap; // rax
  SOCKADDR_IN *v9; // rax
  SOCKADDR_IN *v10; // rdi
  SOCKADDR_IN v11; // xmm0
  PVOID *v12; // r8

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids, NotificationType);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !CallerContext )
  {
    if ( v6 == &WPP_GLOBAL_Control )
      return;
    if ( (*((_BYTE *)v6 + 28) & 1) == 0 || *((_BYTE *)v6 + 25) < 2u )
      goto LABEL_48;
    v7 = 21;
    goto LABEL_46;
  }
  if ( !Row )
  {
    if ( v6 == &WPP_GLOBAL_Control )
      return;
    if ( (*((_BYTE *)v6 + 28) & 1) == 0 || *((_BYTE *)v6 + 25) < 2u )
      goto LABEL_48;
    v7 = 22;
    goto LABEL_46;
  }
  if ( NotificationType == 3 )
  {
    if ( v6 == &WPP_GLOBAL_Control )
      return;
    if ( (*((_BYTE *)v6 + 28) & 1) == 0 || *((_BYTE *)v6 + 25) < 5u )
      goto LABEL_48;
    v7 = 23;
    goto LABEL_46;
  }
  if ( Row->Address.Ipv4.sin_family == 2 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 5u )
      WPP_SF_dd(
        v6[2],
        24,
        WPP_d23f83cd04063ba912a1d720026fb887_Traceguids,
        NotificationType,
        Row->Address.Ipv4.sin_addr.S_un.S_addr);
LABEL_30:
    ProcessHeap = GetProcessHeap();
    v9 = (SOCKADDR_IN *)HeapAlloc(ProcessHeap, 8u, 0x68u);
    v10 = v9;
    if ( v9 )
    {
      memset_0(v9, 0, 0x68u);
      *v10 = Row->Address.Ipv4;
      v10[1] = *((SOCKADDR_IN *)&Row->Address.si_family + 1);
      v10[2] = *(SOCKADDR_IN *)&Row->InterfaceLuid.Value;
      v10[3] = *(SOCKADDR_IN *)&Row->SuffixOrigin;
      v11 = *(SOCKADDR_IN *)&Row->DadState;
      *(_DWORD *)&v10[5].sin_family = NotificationType;
      v10[4] = v11;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          WPP_d23f83cd04063ba912a1d720026fb887_Traceguids,
          *(unsigned int *)v10[2].sin_zero,
          NotificationType);
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(CallerContext + 88));
      v12 = (PVOID *)*((_QWORD *)CallerContext + 18);
      if ( *v12 != CallerContext + 136 )
        __fastfail(3u);
      *(_QWORD *)v10[5].sin_zero = CallerContext + 136;
      *(_QWORD *)&v10[6].sin_family = v12;
      *v12 = v10[5].sin_zero;
      *((_QWORD *)CallerContext + 18) = (char *)v10 + 88;
      LeaveCriticalSection((LPCRITICAL_SECTION)(CallerContext + 88));
      SubmitThreadpoolWork(*((PTP_WORK *)CallerContext + 10));
      goto LABEL_47;
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_48;
    v7 = 27;
LABEL_46:
    WPP_SF_(v6[2], v7, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids);
LABEL_47:
    v6 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_48;
  }
  if ( Row->Address.Ipv4.sin_family == 23 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 5u )
      WPP_SF_d(v6[2], 25, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids, NotificationType);
    goto LABEL_30;
  }
  if ( v6 == &WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
  {
    v7 = 26;
    goto LABEL_46;
  }
LABEL_48:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 6u )
    WPP_SF_(v6[2], 29, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids);
}

```

## disassembly

```asm
0x180057850  push    rbx
0x180057852  push    rbp
0x180057853  push    rsi
0x180057854  push    rdi
0x180057855  push    r12
0x180057857  push    r13
0x180057859  push    r14
0x18005785b  sub     rsp, 30h
0x18005785f  mov     esi, r8d
0x180057862  mov     r14, rdx
0x180057865  mov     rbp, rcx
0x180057868  mov     rcx, cs:WPP_GLOBAL_Control
0x18005786f  lea     r12, WPP_GLOBAL_Control
0x180057876  lea     r13, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids
0x18005787d  cmp     rcx, r12
0x180057880  jz      short loc_1800578A9
0x180057882  test    byte ptr [rcx+1Ch], 1
0x180057886  jz      short loc_1800578A9
0x180057888  cmp     byte ptr [rcx+19h], 6
0x18005788c  jb      short loc_1800578A9
0x18005788e  mov     rcx, [rcx+10h]
0x180057892  mov     r9d, r8d
0x180057895  mov     r8, r13
0x180057898  mov     edx, 14h
0x18005789d  call    WPP_SF_d
0x1800578a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800578a9  test    rbp, rbp
0x1800578ac  jnz     short loc_1800578D5
0x1800578ae  cmp     rcx, r12
0x1800578b1  jz      loc_180057AE1
0x1800578b7  test    byte ptr [rcx+1Ch], 1
0x1800578bb  jz      loc_180057ABF
0x1800578c1  lea     ebx, [rbp+2]
0x1800578c4  cmp     [rcx+19h], bl
0x1800578c7  jb      loc_180057ABF
0x1800578cd  lea     edx, [rbp+15h]
0x1800578d0  jmp     loc_180057AAC
0x1800578d5  test    r14, r14
0x1800578d8  jnz     short loc_180057902
0x1800578da  cmp     rcx, r12
0x1800578dd  jz      loc_180057AE1
0x1800578e3  test    byte ptr [rcx+1Ch], 1
0x1800578e7  jz      loc_180057ABF
0x1800578ed  lea     ebx, [r14+2]
0x1800578f1  cmp     [rcx+19h], bl
0x1800578f4  jb      loc_180057ABF
0x1800578fa  lea     edx, [rbx+14h]
0x1800578fd  jmp     loc_180057AAC
0x180057902  cmp     esi, 3
0x180057905  jnz     short loc_18005792C
0x180057907  cmp     rcx, r12
0x18005790a  jz      loc_180057AE1
0x180057910  test    byte ptr [rcx+1Ch], 1
0x180057914  jz      loc_180057ABF
0x18005791a  cmp     byte ptr [rcx+19h], 5
0x18005791e  jb      loc_180057ABF
0x180057924  lea     edx, [rsi+14h]
0x180057927  jmp     loc_180057AAC
0x18005792c  mov     ebx, 2
0x180057931  cmp     bx, [r14]
0x180057935  jnz     short loc_180057964
0x180057937  cmp     rcx, r12
0x18005793a  jz      short loc_180057996
0x18005793c  test    byte ptr [rcx+1Ch], 1
0x180057940  jz      short loc_180057996
0x180057942  cmp     byte ptr [rcx+19h], 5
0x180057946  jb      short loc_180057996
0x180057948  mov     eax, [r14+4]
0x18005794c  lea     edx, [rbx+16h]
0x18005794f  mov     rcx, [rcx+10h]
0x180057953  mov     r9d, esi
0x180057956  mov     r8, r13
0x180057959  mov     [rsp+68h+var_48], eax
0x18005795d  call    WPP_SF_dd
0x180057962  jmp     short loc_180057996
0x180057964  mov     eax, 17h
0x180057969  cmp     ax, [r14]
0x18005796d  jnz     loc_180057A97
0x180057973  cmp     rcx, r12
0x180057976  jz      short loc_180057996
0x180057978  test    byte ptr [rcx+1Ch], 1
0x18005797c  jz      short loc_180057996
0x18005797e  cmp     byte ptr [rcx+19h], 5
0x180057982  jb      short loc_180057996
0x180057984  mov     rcx, [rcx+10h]
0x180057988  lea     edx, [rax+2]
0x18005798b  mov     r9d, esi
0x18005798e  mov     r8, r13
0x180057991  call    WPP_SF_d
0x180057996  call    cs:__imp_GetProcessHeap
0x18005799c  mov     edx, 8; dwFlags
0x1800579a1  mov     rcx, rax; hHeap
0x1800579a4  lea     r8d, [rdx+60h]; dwBytes
0x1800579a8  call    cs:__imp_HeapAlloc
0x1800579ae  mov     rdi, rax
0x1800579b1  test    rax, rax
0x1800579b4  jnz     short loc_1800579E1
0x1800579b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800579bd  cmp     rcx, r12
0x1800579c0  jz      loc_180057AE1
0x1800579c6  test    byte ptr [rcx+1Ch], 1
0x1800579ca  jz      loc_180057ABF
0x1800579d0  cmp     [rcx+19h], bl
0x1800579d3  jb      loc_180057ABF
0x1800579d9  lea     edx, [rax+1Bh]
0x1800579dc  jmp     loc_180057AAC
0x1800579e1  xor     edx, edx; Val
0x1800579e3  mov     rcx, rdi; void *
0x1800579e6  lea     r8d, [rdx+68h]; Size
0x1800579ea  call    memset_0
0x1800579ef  movups  xmm0, xmmword ptr [r14]
0x1800579f3  movups  xmmword ptr [rdi], xmm0
0x1800579f6  movups  xmm1, xmmword ptr [r14+10h]
0x1800579fb  movups  xmmword ptr [rdi+10h], xmm1
0x1800579ff  movups  xmm0, xmmword ptr [r14+20h]
0x180057a04  movups  xmmword ptr [rdi+20h], xmm0
0x180057a08  movups  xmm1, xmmword ptr [r14+30h]
0x180057a0d  movups  xmmword ptr [rdi+30h], xmm1
0x180057a11  movups  xmm0, xmmword ptr [r14+40h]
0x180057a16  mov     [rdi+50h], esi
0x180057a19  movups  xmmword ptr [rdi+40h], xmm0
0x180057a1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180057a24  cmp     rcx, r12
0x180057a27  jz      short loc_180057A4E
0x180057a29  test    byte ptr [rcx+1Ch], 1
0x180057a2d  jz      short loc_180057A4E
0x180057a2f  cmp     byte ptr [rcx+19h], 5
0x180057a33  jb      short loc_180057A4E
0x180057a35  mov     r9d, [rdi+28h]
0x180057a39  mov     edx, 1Ch
0x180057a3e  mov     rcx, [rcx+10h]
0x180057a42  mov     r8, r13
0x180057a45  mov     [rsp+68h+var_48], esi
0x180057a49  call    WPP_SF_dd
0x180057a4e  lea     rcx, [rbp+58h]; lpCriticalSection
0x180057a52  call    cs:__imp_EnterCriticalSection
0x180057a58  lea     rdx, [rbp+88h]
0x180057a5f  mov     r8, [rdx+8]
0x180057a63  cmp     [r8], rdx
0x180057a66  jz      short loc_180057A6F
0x180057a68  mov     ecx, 3
0x180057a6d  int     29h; Win8: RtlFailFast(ecx)
0x180057a6f  lea     rax, [rdi+58h]
0x180057a73  mov     [rax], rdx
0x180057a76  lea     rcx, [rbp+58h]; lpCriticalSection
0x180057a7a  mov     [rax+8], r8
0x180057a7e  mov     [r8], rax
0x180057a81  mov     [rdx+8], rax
0x180057a85  call    cs:__imp_LeaveCriticalSection
0x180057a8b  mov     rcx, [rbp+50h]; pwk
0x180057a8f  call    cs:__imp_SubmitThreadpoolWork
0x180057a95  jmp     short loc_180057AB8
0x180057a97  cmp     rcx, r12
0x180057a9a  jz      short loc_180057AE1
0x180057a9c  test    byte ptr [rcx+1Ch], 1
0x180057aa0  jz      short loc_180057ABF
0x180057aa2  cmp     [rcx+19h], bl
0x180057aa5  jb      short loc_180057ABF
0x180057aa7  mov     edx, 1Ah
0x180057aac  mov     rcx, [rcx+10h]
0x180057ab0  mov     r8, r13
0x180057ab3  call    WPP_SF_
0x180057ab8  mov     rcx, cs:WPP_GLOBAL_Control
0x180057abf  cmp     rcx, r12
0x180057ac2  jz      short loc_180057AE1
0x180057ac4  test    byte ptr [rcx+1Ch], 1
0x180057ac8  jz      short loc_180057AE1
0x180057aca  cmp     byte ptr [rcx+19h], 6
0x180057ace  jb      short loc_180057AE1
0x180057ad0  mov     rcx, [rcx+10h]
0x180057ad4  mov     edx, 1Dh
0x180057ad9  mov     r8, r13
0x180057adc  call    WPP_SF_
0x180057ae1  add     rsp, 30h
0x180057ae5  pop     r14
0x180057ae7  pop     r13
0x180057ae9  pop     r12
0x180057aeb  pop     rdi
0x180057aec  pop     rsi
0x180057aed  pop     rbp
0x180057aee  pop     rbx
0x180057aef  retn
```
