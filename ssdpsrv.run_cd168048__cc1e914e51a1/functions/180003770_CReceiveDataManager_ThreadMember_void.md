# CReceiveDataManager::ThreadMember(void)

- ea: `0x180003770`
- end: `0x180003a5a`
- name: `?ThreadMember@CReceiveDataManager@@AEAAKXZ`
- size: `746`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180032340`

## callees

- `0x180003770`
- `0x180003a60`
- `0x180003dc0`
- `0x1800040e0`
- `0x180008190`
- `0x1800271fc`
- `0x1800287d0`
- `0x180029df0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800039ce`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800039e6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800039ce`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800039e6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003963`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003963`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000381d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003889`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000381d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003889`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800037f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800037f6`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800037b5`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180003841`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800037b5`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180003841`

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
        if ( (unsigned int)ParseSsdpRequest(v20, v26, Flink_high, (struct _SSDP_REQUEST *)&v29) )
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
      UnreferenceSocket((unsigned __int64)v2->ProcessLocksList.Flink);
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
0x180003770  push    rbp
0x180003772  push    rdi
0x180003773  lea     rbp, [rsp-58h]
0x180003778  sub     rsp, 158h
0x18000377f  mov     rax, cs:__security_cookie
0x180003786  xor     rax, rsp
0x180003789  mov     [rbp+60h+var_20], rax
0x18000378d  mov     rax, [rcx+40h]
0x180003791  lea     rdx, [rsp+160h+Handles]; lpHandles
0x180003796  mov     [rsp+160h+Handles], rax
0x18000379b  mov     rdi, rcx
0x18000379e  mov     rax, [rcx+38h]
0x1800037a2  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x1800037a8  mov     ecx, 2; nCount
0x1800037ad  mov     [rsp+160h+var_138], rax
0x1800037b2  xor     r8d, r8d; bWaitAll
0x1800037b5  call    cs:__imp_WaitForMultipleObjects
0x1800037bc  nop     dword ptr [rax+rax+00h]
0x1800037c1  test    eax, eax
0x1800037c3  jnz     loc_180003869
0x1800037c9  mov     [rsp+160h+arg_8], rbx
0x1800037d1  mov     [rsp+160h+arg_10], rsi
0x1800037d9  xor     esi, esi
0x1800037db  mov     [rsp+160h+var_10], r14
0x1800037e3  lea     r14, WPP_GLOBAL_Control
0x1800037ea  nop     word ptr [rax+rax+00h]
0x1800037f0  mov     rcx, rdi; lpCriticalSection
0x1800037f3  mov     rbx, rsi
0x1800037f6  call    cs:__imp_EnterCriticalSection
0x1800037fd  nop     dword ptr [rax+rax+00h]
0x180003802  mov     rax, [rdi+28h]
0x180003806  test    rax, rax
0x180003809  jz      short loc_18000381A
0x18000380b  mov     rbx, rax
0x18000380e  mov     rax, [rax]
0x180003811  mov     [rdi+28h], rax
0x180003815  test    rax, rax
0x180003818  jz      short loc_180003882
0x18000381a  mov     rcx, rdi; lpCriticalSection
0x18000381d  call    cs:__imp_LeaveCriticalSection
0x180003824  nop     dword ptr [rax+rax+00h]
0x180003829  test    rbx, rbx
0x18000382c  jnz     short loc_180003895
0x18000382e  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x180003834  lea     rdx, [rsp+160h+Handles]; lpHandles
0x180003839  xor     r8d, r8d; bWaitAll
0x18000383c  mov     ecx, 2; nCount
0x180003841  call    cs:__imp_WaitForMultipleObjects
0x180003848  nop     dword ptr [rax+rax+00h]
0x18000384d  test    eax, eax
0x18000384f  jz      short loc_1800037F0
0x180003851  mov     r14, [rsp+160h+var_10]
0x180003859  mov     rsi, [rsp+160h+arg_10]
0x180003861  mov     rbx, [rsp+160h+arg_8]
0x180003869  xor     eax, eax
0x18000386b  mov     rcx, [rbp+60h+var_20]
0x18000386f  xor     rcx, rsp; StackCookie
0x180003872  call    __security_check_cookie
0x180003877  add     rsp, 158h
0x18000387e  pop     rdi
0x18000387f  pop     rbp
0x180003880  retn
0x180003882  mov     rcx, rdi; lpCriticalSection
0x180003885  mov     [rdi+30h], rsi
0x180003889  call    cs:__imp_LeaveCriticalSection
0x180003890  nop     dword ptr [rax+rax+00h]
0x180003895  movups  xmm1, xmmword ptr [rbx+28h]
0x180003899  xor     eax, eax
0x18000389b  mov     ecx, 0A0h; Size
0x1800038a0  xorps   xmm0, xmm0
0x1800038a3  mov     [rbp+60h+var_8C], eax
0x1800038a6  mov     rax, [rbx+10h]
0x1800038aa  movaps  [rsp+160h+var_110], xmm0
0x1800038af  movaps  [rsp+160h+var_100], xmm0
0x1800038b4  movaps  [rsp+160h+var_F0], xmm0
0x1800038b9  movaps  [rbp+60h+var_E0], xmm0
0x1800038bd  movaps  [rbp+60h+var_D0], xmm0
0x1800038c1  movaps  [rbp+60h+var_C0], xmm0
0x1800038c5  movaps  [rbp+60h+var_B0], xmm0
0x1800038c9  movaps  [rsp+160h+var_120], xmm0
0x1800038ce  movups  xmm0, xmmword ptr [rbx+18h]
0x1800038d2  mov     [rsp+160h+var_130], rax
0x1800038d7  mov     rax, [rbx+8]
0x1800038db  movups  [rsp+160h+var_120+8], xmm0
0x1800038e0  mov     [rsp+160h+var_128], rax
0x1800038e5  movups  xmm0, xmmword ptr [rbx+38h]
0x1800038e9  mov     eax, [rbx+98h]
0x1800038ef  movups  [rsp+160h+var_110+8], xmm1
0x1800038f4  mov     [rbp+60h+var_98], eax
0x1800038f7  movups  xmm1, xmmword ptr [rbx+48h]
0x1800038fb  mov     eax, [rbx+9Ch]
0x180003901  movups  [rsp+160h+var_100+8], xmm0
0x180003906  mov     [rbp+60h+var_94], eax
0x180003909  movups  xmm0, xmmword ptr [rbx+58h]
0x18000390d  mov     eax, [rbx+0A0h]
0x180003913  movups  [rsp+160h+var_F0+8], xmm1
0x180003918  mov     [rbp+60h+var_90], eax
0x18000391b  movups  xmm1, xmmword ptr [rbx+68h]
0x18000391f  movups  [rbp+60h+var_E0+8], xmm0
0x180003923  movups  xmm0, xmmword ptr [rbx+78h]
0x180003927  movups  [rbp+60h+var_D0+8], xmm1
0x18000392b  movups  xmm1, xmmword ptr [rbx+88h]
0x180003932  movups  [rbp+60h+var_C0+8], xmm0
0x180003936  xorps   xmm0, xmm0
0x180003939  movups  [rbp+60h+var_80], xmm0
0x18000393d  mov     dword ptr [rbp+60h+var_80], 4
0x180003944  movups  [rbp+60h+var_40], xmm0
0x180003948  mov     qword ptr [rbp+60h+var_80+8], rsi
0x18000394c  mov     dword ptr [rbp+60h+var_40+8], 14h
0x180003953  movups  [rbp+60h+var_B0+8], xmm1
0x180003957  movups  [rbp+60h+var_70], xmm0
0x18000395b  movups  [rbp+60h+var_60], xmm0
0x18000395f  movups  [rbp+60h+var_50], xmm0
0x180003963  call    cs:__imp_malloc
0x18000396a  nop     dword ptr [rax+rax+00h]
0x18000396f  mov     [rbp+60h+var_30], rax
0x180003973  mov     rdx, rax
0x180003976  test    rax, rax
0x180003979  jz      loc_180003A0E
0x18000397f  mov     eax, esi
0x180003981  mov     ecx, eax
0x180003983  inc     eax
0x180003985  mov     [rdx+rcx*8], rsi
0x180003989  cmp     eax, dword ptr [rbp+60h+var_40+8]
0x18000398c  jnb     short loc_180003994
0x18000398e  mov     rdx, [rbp+60h+var_30]
0x180003992  jmp     short loc_180003981
0x180003994  mov     r8d, [rbx+0A4h]; unsigned int
0x18000399b  lea     r9, [rbp+60h+var_80]; struct _SSDP_REQUEST *
0x18000399f  mov     edx, [rbp+60h+var_94]; unsigned int
0x1800039a2  xorps   xmm0, xmm0
0x1800039a5  mov     rcx, [rbx+8]; char *
0x1800039a9  movdqa  [rbp+60h+var_70], xmm0
0x1800039ae  call    ?ParseSsdpRequest@@YAHPEADKKPEAU_SSDP_REQUEST@@@Z; ParseSsdpRequest(char *,ulong,ulong,_SSDP_REQUEST *)
0x1800039b3  test    eax, eax
0x1800039b5  jz      short loc_1800039F7
0x1800039b7  lea     rdx, [rsp+160h+var_130]; struct _RECEIVE_DATA *
0x1800039bc  lea     rcx, [rbp+60h+var_80]; struct _SSDP_REQUEST *
0x1800039c0  call    ?ProcessSsdpRequest@@YAXPEAU_SSDP_REQUEST@@PEAU_RECEIVE_DATA@@@Z; ProcessSsdpRequest(_SSDP_REQUEST *,_RECEIVE_DATA *)
0x1800039c5  mov     rcx, [rbx+8]; Block
0x1800039c9  test    rcx, rcx
0x1800039cc  jz      short loc_1800039DA
0x1800039ce  call    cs:__imp_free
0x1800039d5  nop     dword ptr [rax+rax+00h]
0x1800039da  mov     rcx, [rbx+10h]; unsigned __int64
0x1800039de  call    ?UnreferenceSocket@@YAX_K@Z; UnreferenceSocket(unsigned __int64)
0x1800039e3  mov     rcx, rbx; Block
0x1800039e6  call    cs:__imp_free
0x1800039ed  nop     dword ptr [rax+rax+00h]
0x1800039f2  jmp     loc_1800037F0
0x1800039f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039fe  cmp     rcx, r14
0x180003a01  jnz     short loc_180003A3D
0x180003a03  lea     rcx, [rbp+60h+var_80]; struct _SSDP_REQUEST *
0x180003a07  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x180003a0c  jmp     short loc_1800039C5
0x180003a0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a15  cmp     rcx, r14
0x180003a18  jz      short loc_1800039C5
0x180003a1a  test    byte ptr [rcx+1Ch], 1
0x180003a1e  jz      short loc_1800039C5
0x180003a20  mov     rcx, [rcx+10h]
0x180003a24  lea     r8, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids
0x180003a2b  mov     edx, 3Dh ; '='
0x180003a30  mov     r9d, 8007000Eh
0x180003a36  call    WPP_SF_d
0x180003a3b  jmp     short loc_1800039C5
0x180003a3d  test    byte ptr [rcx+1Ch], 8
0x180003a41  jz      short loc_180003A03
0x180003a43  mov     rcx, [rcx+10h]
0x180003a47  lea     r8, WPP_bc52afbc171436f214070148f5e15db4_Traceguids
0x180003a4e  mov     edx, 0Eh
0x180003a53  call    WPP_SF_
0x180003a58  jmp     short loc_180003A03
```
