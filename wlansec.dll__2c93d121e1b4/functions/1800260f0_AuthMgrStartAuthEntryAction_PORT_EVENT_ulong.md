# AuthMgrStartAuthEntryAction(PORT_EVENT *,ulong *)

- ea: `0x1800260f0`
- end: `0x1800262a3`
- name: `?AuthMgrStartAuthEntryAction@@YAKPEAUPORT_EVENT@@PEAK@Z`
- size: `435`
- prototype: `unsigned int __fastcall(struct PORT_EVENT *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000c444`
- `0x1800169c0`
- `0x1800260f0`
- `0x1800262ac`

## import_xrefs

- `OneX!OneXStartAuthentication` at `0x1800261fb`
- `OneX!OneXStartAuthentication` at `0x1800261fb`
- `MobileNetworking!ReleaseWriteLock` at `0x18002625c`
- `MobileNetworking!ReleaseWriteLock` at `0x18002625c`
- `MobileNetworking!AcquireWriteLock` at `0x180026178`
- `MobileNetworking!AcquireWriteLock` at `0x180026178`

## pseudocode

```c
__int64 __fastcall AuthMgrStartAuthEntryAction(struct PORT_EVENT *a1, unsigned int *a2)
{
  __int64 v3; // rdi
  __int64 v4; // rsi
  unsigned int v5; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 69, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids);
  v3 = *((_QWORD *)a1 + 3);
  *(_DWORD *)(v3 + 936) = _InterlockedIncrement((volatile signed __int32 *)&qword_1800AEFB0);
  v4 = *(_QWORD *)(v3 + 24);
  TraceAdapterId(*(_DWORD *)(v4 + 2496), ">>> Locking >>>");
  AcquireWriteLock(v4, v4 + 2512, "AuthMgrStartAuthEntryAction", 767);
  v5 = AuthMgrPreConnectConfigureOneX(
         *(void **)(v3 + 928),
         *(_DWORD *)(*(_QWORD *)(v4 + 2784) + 40LL),
         *(void **)(*(_QWORD *)(v4 + 2784) + 48LL),
         *(struct DOT11_MSMSEC_RUNTIME_STATE **)(v4 + 2904),
         **(_DWORD **)(*(_QWORD *)(v4 + 2784) + 24LL) == 8);
  v6 = v5;
  if ( v5 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v8 = 70;
LABEL_8:
      WPP_SF_d(v7[7], v8, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids, v5);
    }
  }
  else
  {
    v5 = OneXStartAuthentication(1, *(unsigned int *)(v3 + 936), *(_QWORD *)(v3 + 928), 0);
    v6 = v5;
    if ( !v5 )
    {
      v6 = CreateAndQueuePortEvent(v3, 37, 0);
      goto LABEL_14;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v8 = 71;
      goto LABEL_8;
    }
  }
LABEL_14:
  TraceAdapterId(*(_DWORD *)(v4 + 2496), "<<< Unlocking <<<");
  ReleaseWriteLock(v4, v4 + 2512, "AuthMgrStartAuthEntryAction", 791);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 72, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x1800260f0  push    rbx
0x1800260f2  push    rbp
0x1800260f3  push    rsi
0x1800260f4  push    rdi
0x1800260f5  push    r15
0x1800260f7  sub     rsp, 30h
0x1800260fb  mov     rdi, rcx
0x1800260fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180026105  lea     r15, WPP_GLOBAL_Control
0x18002610c  cmp     rcx, r15
0x18002610f  jz      short loc_18002612F
0x180026111  test    dword ptr [rcx+44h], 100h
0x180026118  jz      short loc_18002612F
0x18002611a  mov     rcx, [rcx+38h]
0x18002611e  lea     r8, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids
0x180026125  mov     edx, 45h ; 'E'
0x18002612a  call    WPP_SF_
0x18002612f  mov     rdi, [rdi+18h]
0x180026133  mov     eax, 1
0x180026138  lock xadd dword ptr cs:qword_1800AEFB0, eax
0x180026140  inc     eax
0x180026142  lea     rdx, aLocking; ">>> Locking >>>"
0x180026149  mov     [rdi+3A8h], eax
0x18002614f  mov     rsi, [rdi+18h]
0x180026153  mov     ecx, [rsi+9C0h]; unsigned int
0x180026159  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18002615e  lea     rbp, [rsi+9D0h]
0x180026165  mov     r9d, 2FFh
0x18002616b  mov     rdx, rbp
0x18002616e  lea     r8, aAuthmgrstartau; "AuthMgrStartAuthEntryAction"
0x180026175  mov     rcx, rsi
0x180026178  call    cs:__imp_AcquireWriteLock
0x18002617f  nop     dword ptr [rax+rax+00h]
0x180026184  mov     rdx, [rsi+0AE0h]
0x18002618b  xor     ecx, ecx
0x18002618d  mov     r9, [rsi+0B58h]; struct DOT11_MSMSEC_RUNTIME_STATE *
0x180026194  mov     rax, [rdx+18h]
0x180026198  mov     r8, [rdx+30h]; void *
0x18002619c  mov     edx, [rdx+28h]; unsigned int
0x18002619f  cmp     dword ptr [rax], 8
0x1800261a2  setz    cl
0x1800261a5  mov     [rsp+58h+var_38], ecx; int
0x1800261a9  mov     rcx, [rdi+3A0h]; void *
0x1800261b0  call    ?AuthMgrPreConnectConfigureOneX@@YAKPEAXK0PEAUDOT11_MSMSEC_RUNTIME_STATE@@H@Z; AuthMgrPreConnectConfigureOneX(void *,ulong,void *,DOT11_MSMSEC_RUNTIME_STATE *,int)
0x1800261b5  mov     ebx, eax
0x1800261b7  test    eax, eax
0x1800261b9  jz      short loc_1800261E7
0x1800261bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800261c2  cmp     rcx, r15
0x1800261c5  jz      short loc_180026237
0x1800261c7  test    byte ptr [rcx+44h], 1
0x1800261cb  jz      short loc_180026237
0x1800261cd  mov     edx, 46h ; 'F'
0x1800261d2  mov     rcx, [rcx+38h]
0x1800261d6  lea     r8, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids
0x1800261dd  mov     r9d, eax
0x1800261e0  call    WPP_SF_d
0x1800261e5  jmp     short loc_180026237
0x1800261e7  mov     edx, [rdi+3A8h]
0x1800261ed  xor     r9d, r9d
0x1800261f0  mov     r8, [rdi+3A0h]
0x1800261f7  lea     ecx, [r9+1]
0x1800261fb  call    cs:__imp_OneXStartAuthentication
0x180026202  nop     dword ptr [rax+rax+00h]
0x180026207  mov     ebx, eax
0x180026209  test    eax, eax
0x18002620b  jz      short loc_180026226
0x18002620d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026214  cmp     rcx, r15
0x180026217  jz      short loc_180026237
0x180026219  test    byte ptr [rcx+44h], 1
0x18002621d  jz      short loc_180026237
0x18002621f  mov     edx, 47h ; 'G'
0x180026224  jmp     short loc_1800261D2
0x180026226  xor     r8d, r8d
0x180026229  mov     rcx, rdi
0x18002622c  lea     edx, [r8+25h]
0x180026230  call    ?CreateAndQueuePortEvent@@YAKPEAUMSMSEC_PORT_CONTEXT@@W4MSMSEC_PORT_EVENT_TYPE@@H@Z; CreateAndQueuePortEvent(MSMSEC_PORT_CONTEXT *,MSMSEC_PORT_EVENT_TYPE,int)
0x180026235  mov     ebx, eax
0x180026237  mov     ecx, [rsi+9C0h]; unsigned int
0x18002623d  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180026244  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180026249  mov     r9d, 317h
0x18002624f  lea     r8, aAuthmgrstartau; "AuthMgrStartAuthEntryAction"
0x180026256  mov     rdx, rbp
0x180026259  mov     rcx, rsi
0x18002625c  call    cs:__imp_ReleaseWriteLock
0x180026263  nop     dword ptr [rax+rax+00h]
0x180026268  mov     rcx, cs:WPP_GLOBAL_Control
0x18002626f  cmp     rcx, r15
0x180026272  jz      short loc_180026295
0x180026274  test    dword ptr [rcx+44h], 100h
0x18002627b  jz      short loc_180026295
0x18002627d  mov     rcx, [rcx+38h]
0x180026281  lea     r8, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids
0x180026288  mov     edx, 48h ; 'H'
0x18002628d  mov     r9d, ebx
0x180026290  call    WPP_SF_d
0x180026295  mov     eax, ebx
0x180026297  add     rsp, 30h
0x18002629b  pop     r15
0x18002629d  pop     rdi
0x18002629e  pop     rsi
0x18002629f  pop     rbp
0x1800262a0  pop     rbx
0x1800262a1  retn
```
