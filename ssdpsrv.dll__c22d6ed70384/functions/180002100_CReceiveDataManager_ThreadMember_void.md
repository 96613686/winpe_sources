# CReceiveDataManager::ThreadMember(void)

- ea: `0x180002100`
- end: `0x1800023bd`
- name: `?ThreadMember@CReceiveDataManager@@AEAAKXZ`
- size: `701`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002fff0`

## callees

- `0x180002100`
- `0x1800023d0`
- `0x1800026b0`
- `0x1800029b0`
- `0x180006d70`
- `0x1800255a8`
- `0x180026a30`
- `0x180028000`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000233d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000234f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000233d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000234f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800022ce`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800022ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000219b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800021fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000219b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800021fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000217a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000217a`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180002145`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800021b9`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180002145`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800021b9`

## pseudocode

```c
__int64 __fastcall CReceiveDataManager::ThreadMember(LPCRITICAL_SECTION lpCriticalSection)
{
  PRTL_CRITICAL_SECTION_DEBUG v2; // rbx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rax
  struct _RTL_CRITICAL_SECTION_DEBUG *v4; // rax
  __int128 v6; // xmm1
  struct _LIST_ENTRY *Flink; // rax
  __int128 v8; // xmm0
  struct _RTL_CRITICAL_SECTION *CriticalSection; // rax
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  _QWORD *v16; // rdx
  unsigned int v17; // eax
  __int64 v18; // rcx
  unsigned int Flink_high; // r8d
  char *v20; // rcx
  struct _RTL_CRITICAL_SECTION *v21; // rcx
  HANDLE Handles[2]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v23[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v24[136]; // [rsp+40h] [rbp-C0h] BYREF
  int v25; // [rsp+C8h] [rbp-38h]
  unsigned int v26; // [rsp+CCh] [rbp-34h]
  int v27; // [rsp+D0h] [rbp-30h]
  int v28; // [rsp+D4h] [rbp-2Ch]
  __int128 v29; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v30; // [rsp+F0h] [rbp-10h]
  __int128 v31; // [rsp+100h] [rbp+0h]
  __int128 v32; // [rsp+110h] [rbp+10h]
  __int128 v33; // [rsp+120h] [rbp+20h]
  _QWORD *v34; // [rsp+130h] [rbp+30h]

  Handles[0] = lpCriticalSection[1].LockSemaphore;
  Handles[1] = lpCriticalSection[1].OwningThread;
  while ( !WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF) )
  {
    while ( 1 )
    {
      v2 = 0;
      EnterCriticalSection(lpCriticalSection);
      DebugInfo = lpCriticalSection[1].DebugInfo;
      if ( !DebugInfo )
        break;
      v2 = lpCriticalSection[1].DebugInfo;
      v4 = *(struct _RTL_CRITICAL_SECTION_DEBUG **)&DebugInfo->Type;
      lpCriticalSection[1].DebugInfo = v4;
      if ( v4 )
        break;
      *(_QWORD *)&lpCriticalSection[1].LockCount = 0;
      LeaveCriticalSection(lpCriticalSection);
LABEL_8:
      v6 = *(_OWORD *)&v2->Flags;
      v28 = 0;
      Flink = v2->ProcessLocksList.Flink;
      memset(&v24[16], 0, 112);
      *(_OWORD *)v24 = 0;
      v8 = *(_OWORD *)&v2->ProcessLocksList.Blink;
      v23[0] = Flink;
      CriticalSection = v2->CriticalSection;
      *(_OWORD *)&v24[8] = v8;
      v23[1] = CriticalSection;
      v10 = *(_OWORD *)&v2[1].CriticalSection;
      LODWORD(CriticalSection) = v2[3].CriticalSection;
      *(_OWORD *)&v24[24] = v6;
      v25 = (int)CriticalSection;
      v11 = *(_OWORD *)&v2[1].ProcessLocksList.Blink;
      LODWORD(CriticalSection) = HIDWORD(v2[3].CriticalSection);
      *(_OWORD *)&v24[40] = v10;
      v26 = (unsigned int)CriticalSection;
      v12 = *(_OWORD *)&v2[1].Flags;
      LODWORD(CriticalSection) = v2[3].ProcessLocksList.Flink;
      *(_OWORD *)&v24[56] = v11;
      v27 = (int)CriticalSection;
      v13 = *(_OWORD *)&v2[2].CriticalSection;
      *(_OWORD *)&v24[72] = v12;
      v14 = *(_OWORD *)&v2[2].ProcessLocksList.Blink;
      *(_OWORD *)&v24[88] = v13;
      v15 = *(_OWORD *)&v2[2].Flags;
      *(_OWORD *)&v24[104] = v14;
      v29 = 4u;
      v33 = 0;
      DWORD2(v33) = 20;
      *(_OWORD *)&v24[120] = v15;
      v30 = 0;
      v31 = 0;
      v32 = 0;
      v34 = malloc(0xA0u);
      v16 = v34;
      if ( v34 )
      {
        v17 = 0;
        while ( 1 )
        {
          v18 = v17++;
          v16[v18] = 0;
          if ( v17 >= DWORD2(v33) )
            break;
          v16 = v34;
        }
        Flink_high = HIDWORD(v2[3].ProcessLocksList.Flink);
        v20 = (char *)v2->CriticalSection;
        v30 = 0;
        if ( ParseSsdpRequest(v20, v26, Flink_high, (struct _SSDP_REQUEST *)&v29) )
        {
          ProcessSsdpRequest((struct _SSDP_REQUEST *)&v29, (struct _RECEIVE_DATA *)v23);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_bc52afbc171436f214070148f5e15db4_Traceguids);
          FreeSsdpRequest((struct _SSDP_REQUEST *)&v29);
        }
      }
      else if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids, 2147942414LL);
      }
      v21 = v2->CriticalSection;
      if ( v21 )
        free(v21);
      UnreferenceSocket((__int64)v2->ProcessLocksList.Flink);
      free(v2);
    }
    LeaveCriticalSection(lpCriticalSection);
    if ( v2 )
      goto LABEL_8;
  }
  return 0;
}

```

## disassembly

```asm
0x180002100  push    rbp
0x180002102  push    rdi
0x180002103  lea     rbp, [rsp-58h]
0x180002108  sub     rsp, 158h
0x18000210f  mov     rax, cs:__security_cookie
0x180002116  xor     rax, rsp
0x180002119  mov     [rbp+60h+var_20], rax
0x18000211d  mov     rax, [rcx+40h]
0x180002121  lea     rdx, [rsp+160h+Handles]; lpHandles
0x180002126  mov     [rsp+160h+Handles], rax
0x18000212b  mov     rdi, rcx
0x18000212e  mov     rax, [rcx+38h]
0x180002132  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x180002138  mov     ecx, 2; nCount
0x18000213d  mov     [rsp+160h+var_138], rax
0x180002142  xor     r8d, r8d; bWaitAll
0x180002145  call    cs:__imp_WaitForMultipleObjects
0x18000214b  test    eax, eax
0x18000214d  jnz     loc_1800021DB
0x180002153  mov     [rsp+160h+arg_8], rbx
0x18000215b  mov     [rsp+160h+arg_10], rsi
0x180002163  xor     esi, esi
0x180002165  mov     [rsp+160h+var_10], r14
0x18000216d  lea     r14, WPP_GLOBAL_Control
0x180002174  mov     rcx, rdi; lpCriticalSection
0x180002177  mov     rbx, rsi
0x18000217a  call    cs:__imp_EnterCriticalSection
0x180002180  mov     rax, [rdi+28h]
0x180002184  test    rax, rax
0x180002187  jz      short loc_180002198
0x180002189  mov     rbx, rax
0x18000218c  mov     rax, [rax]
0x18000218f  mov     [rdi+28h], rax
0x180002193  test    rax, rax
0x180002196  jz      short loc_1800021F3
0x180002198  mov     rcx, rdi; lpCriticalSection
0x18000219b  call    cs:__imp_LeaveCriticalSection
0x1800021a1  test    rbx, rbx
0x1800021a4  jnz     short loc_180002200
0x1800021a6  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x1800021ac  lea     rdx, [rsp+160h+Handles]; lpHandles
0x1800021b1  xor     r8d, r8d; bWaitAll
0x1800021b4  mov     ecx, 2; nCount
0x1800021b9  call    cs:__imp_WaitForMultipleObjects
0x1800021bf  test    eax, eax
0x1800021c1  jz      short loc_180002174
0x1800021c3  mov     r14, [rsp+160h+var_10]
0x1800021cb  mov     rsi, [rsp+160h+arg_10]
0x1800021d3  mov     rbx, [rsp+160h+arg_8]
0x1800021db  xor     eax, eax
0x1800021dd  mov     rcx, [rbp+60h+var_20]
0x1800021e1  xor     rcx, rsp; StackCookie
0x1800021e4  call    __security_check_cookie
0x1800021e9  add     rsp, 158h
0x1800021f0  pop     rdi
0x1800021f1  pop     rbp
0x1800021f2  retn
0x1800021f3  mov     rcx, rdi; lpCriticalSection
0x1800021f6  mov     [rdi+30h], rsi
0x1800021fa  call    cs:__imp_LeaveCriticalSection
0x180002200  movups  xmm1, xmmword ptr [rbx+28h]
0x180002204  xor     eax, eax
0x180002206  mov     ecx, 0A0h; Size
0x18000220b  xorps   xmm0, xmm0
0x18000220e  mov     [rbp+60h+var_8C], eax
0x180002211  mov     rax, [rbx+10h]
0x180002215  movaps  [rsp+160h+var_110], xmm0
0x18000221a  movaps  [rsp+160h+var_100], xmm0
0x18000221f  movaps  [rsp+160h+var_F0], xmm0
0x180002224  movaps  [rbp+60h+var_E0], xmm0
0x180002228  movaps  [rbp+60h+var_D0], xmm0
0x18000222c  movaps  [rbp+60h+var_C0], xmm0
0x180002230  movaps  [rbp+60h+var_B0], xmm0
0x180002234  movaps  [rsp+160h+var_120], xmm0
0x180002239  movups  xmm0, xmmword ptr [rbx+18h]
0x18000223d  mov     [rsp+160h+var_130], rax
0x180002242  mov     rax, [rbx+8]
0x180002246  movups  [rsp+160h+var_120+8], xmm0
0x18000224b  mov     [rsp+160h+var_128], rax
0x180002250  movups  xmm0, xmmword ptr [rbx+38h]
0x180002254  mov     eax, [rbx+98h]
0x18000225a  movups  [rsp+160h+var_110+8], xmm1
0x18000225f  mov     [rbp+60h+var_98], eax
0x180002262  movups  xmm1, xmmword ptr [rbx+48h]
0x180002266  mov     eax, [rbx+9Ch]
0x18000226c  movups  [rsp+160h+var_100+8], xmm0
0x180002271  mov     [rbp+60h+var_94], eax
0x180002274  movups  xmm0, xmmword ptr [rbx+58h]
0x180002278  mov     eax, [rbx+0A0h]
0x18000227e  movups  [rsp+160h+var_F0+8], xmm1
0x180002283  mov     [rbp+60h+var_90], eax
0x180002286  movups  xmm1, xmmword ptr [rbx+68h]
0x18000228a  movups  [rbp+60h+var_E0+8], xmm0
0x18000228e  movups  xmm0, xmmword ptr [rbx+78h]
0x180002292  movups  [rbp+60h+var_D0+8], xmm1
0x180002296  movups  xmm1, xmmword ptr [rbx+88h]
0x18000229d  movups  [rbp+60h+var_C0+8], xmm0
0x1800022a1  xorps   xmm0, xmm0
0x1800022a4  movups  [rbp+60h+var_80], xmm0
0x1800022a8  mov     dword ptr [rbp+60h+var_80], 4
0x1800022af  movups  [rbp+60h+var_40], xmm0
0x1800022b3  mov     qword ptr [rbp+60h+var_80+8], rsi
0x1800022b7  mov     dword ptr [rbp+60h+var_40+8], 14h
0x1800022be  movups  [rbp+60h+var_B0+8], xmm1
0x1800022c2  movups  [rbp+60h+var_70], xmm0
0x1800022c6  movups  [rbp+60h+var_60], xmm0
0x1800022ca  movups  [rbp+60h+var_50], xmm0
0x1800022ce  call    cs:__imp_malloc
0x1800022d4  mov     [rbp+60h+var_30], rax
0x1800022d8  mov     rdx, rax
0x1800022db  test    rax, rax
0x1800022de  jz      loc_180002371
0x1800022e4  mov     eax, esi
0x1800022e6  nop     word ptr [rax+rax+00000000h]
0x1800022f0  mov     ecx, eax
0x1800022f2  inc     eax
0x1800022f4  mov     [rdx+rcx*8], rsi
0x1800022f8  cmp     eax, dword ptr [rbp+60h+var_40+8]
0x1800022fb  jnb     short loc_180002303
0x1800022fd  mov     rdx, [rbp+60h+var_30]
0x180002301  jmp     short loc_1800022F0
0x180002303  mov     r8d, [rbx+0A4h]; unsigned int
0x18000230a  lea     r9, [rbp+60h+var_80]; struct _SSDP_REQUEST *
0x18000230e  mov     edx, [rbp+60h+var_94]; unsigned int
0x180002311  xorps   xmm0, xmm0
0x180002314  mov     rcx, [rbx+8]; char *
0x180002318  movdqa  [rbp+60h+var_70], xmm0
0x18000231d  call    ?ParseSsdpRequest@@YAHPEADKKPEAU_SSDP_REQUEST@@@Z; ParseSsdpRequest(char *,ulong,ulong,_SSDP_REQUEST *)
0x180002322  test    eax, eax
0x180002324  jz      short loc_18000235A
0x180002326  lea     rdx, [rsp+160h+var_130]; struct _RECEIVE_DATA *
0x18000232b  lea     rcx, [rbp+60h+var_80]; struct _SSDP_REQUEST *
0x18000232f  call    ?ProcessSsdpRequest@@YAXPEAU_SSDP_REQUEST@@PEAU_RECEIVE_DATA@@@Z; ProcessSsdpRequest(_SSDP_REQUEST *,_RECEIVE_DATA *)
0x180002334  mov     rcx, [rbx+8]; Block
0x180002338  test    rcx, rcx
0x18000233b  jz      short loc_180002343
0x18000233d  call    cs:__imp_free
0x180002343  mov     rcx, [rbx+10h]; unsigned __int64
0x180002347  call    ?UnreferenceSocket@@YAX_K@Z; UnreferenceSocket(unsigned __int64)
0x18000234c  mov     rcx, rbx; Block
0x18000234f  call    cs:__imp_free
0x180002355  jmp     loc_180002174
0x18000235a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002361  cmp     rcx, r14
0x180002364  jnz     short loc_1800023A0
0x180002366  lea     rcx, [rbp+60h+var_80]; struct _SSDP_REQUEST *
0x18000236a  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x18000236f  jmp     short loc_180002334
0x180002371  mov     rcx, cs:WPP_GLOBAL_Control
0x180002378  cmp     rcx, r14
0x18000237b  jz      short loc_180002334
0x18000237d  test    byte ptr [rcx+1Ch], 1
0x180002381  jz      short loc_180002334
0x180002383  mov     rcx, [rcx+10h]
0x180002387  lea     r8, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids
0x18000238e  mov     edx, 3Dh ; '='
0x180002393  mov     r9d, 8007000Eh
0x180002399  call    WPP_SF_d
0x18000239e  jmp     short loc_180002334
0x1800023a0  test    byte ptr [rcx+1Ch], 8
0x1800023a4  jz      short loc_180002366
0x1800023a6  mov     rcx, [rcx+10h]
0x1800023aa  lea     r8, WPP_bc52afbc171436f214070148f5e15db4_Traceguids
0x1800023b1  mov     edx, 0Eh
0x1800023b6  call    WPP_SF_
0x1800023bb  jmp     short loc_180002366
```
