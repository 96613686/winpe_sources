# SecMgrSetPortParams(MSMSEC_PORT_CONTEXT *,void *,_DOT11_PORT_STATE *,ulong,DOT11_ASSOCIATION_COMPLETION_PARAMETERS *)

- ea: `0x1800166b4`
- end: `0x1800169b9`
- name: `?SecMgrSetPortParams@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAXPEAU_DOT11_PORT_STATE@@KPEAUDOT11_ASSOCIATION_COMPLETION_PARAMETERS@@@Z`
- size: `773`
- prototype: `unsigned int __usercall@<eax>(struct MSMSEC_PORT_CONTEXT *@<rcx>, void *@<rdx>, struct _DOT11_PORT_STATE *@<r8>, unsigned int@<r9d>, struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180015600`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000c730`
- `0x1800166b4`
- `0x1800169c0`
- `0x180016bdc`
- `0x180016e28`
- `0x180016f04`
- `0x180016f74`
- `0x180033678`
- `0x180034a34`
- `0x180044554`
- `0x180055a38`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18001682d`
- `MobileNetworking!ReleaseWriteLock` at `0x18001682d`
- `MobileNetworking!AcquireWriteLock` at `0x180016782`
- `MobileNetworking!AcquireWriteLock` at `0x180016782`

## pseudocode

```c
__int64 __fastcall SecMgrSetPortParams(
        struct MSMSEC_PORT_CONTEXT *a1,
        void *a2,
        struct _DOT11_PORT_STATE *a3,
        unsigned int a4,
        struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *Src)
{
  size_t v5; // rbp
  PVOID *v9; // rcx
  unsigned int MSMSecMemory; // eax
  unsigned int v11; // ebx
  int v12; // r8d
  unsigned int v13; // eax
  PVOID *v14; // rcx
  _QWORD *v16; // rcx
  __int64 v17; // rdx

  v5 = a4;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 66, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 68) & 2) != 0 )
      WPP_SF_(v9[7], 67, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids);
  }
  *(_DWORD *)((char *)a1 + 302) = *(_DWORD *)a3->PeerMacAddress;
  *((_WORD *)a1 + 153) = *(_WORD *)&a3->PeerMacAddress[4];
  SecMgrSetMSMPortHandle(a1, a2);
  MSMSecMemory = AllocateMSMSecMemory((unsigned int)v5);
  v11 = MSMSecMemory;
  if ( !MSMSecMemory )
  {
    memcpy_0(*((void **)a1 + 61), Src, v5);
    *((_QWORD *)a1 + 62) = 1;
    FlushKeyCache((struct MSMSEC_PORT_CONTEXT *)((char *)a1 + 776));
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
      WPP_SF_Ls(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        11,
        v12,
        *(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL),
        (__int64)">>> Locking >>>");
    AcquireWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "SecMgrSetPortParams", 967);
    v13 = KeyMgrSetPortParams(
            a1,
            (struct MSMSEC_HOST_DESC *)(*((_QWORD *)a1 + 3) + 2776LL),
            *(const struct DOT11_MSMSEC_CONNECTION_PROFILE **)(*((_QWORD *)a1 + 3) + 2784LL));
    v11 = v13;
    if ( v13 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_10;
      v17 = 69;
    }
    else
    {
      v13 = AuthMgrSetPortParams(a1);
      v11 = v13;
      if ( v13 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_10;
        v17 = 70;
      }
      else
      {
        v13 = KeyCacheSetPortParams(
                (char *)a1 + 776,
                (unsigned int)(*((_DWORD *)a1 + 230) - 1) > 1,
                *((unsigned int *)a1 + 250));
        v11 = v13;
        if ( v13 )
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            goto LABEL_10;
          v17 = 71;
        }
        else
        {
          v13 = WpsAuthMgrSetPortParams(a1);
          v11 = v13;
          if ( !v13 )
            goto LABEL_10;
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            goto LABEL_10;
          v17 = 72;
        }
      }
    }
    WPP_SF_d(v16[7], v17, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v13);
LABEL_10:
    TraceAdapterId(*(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL), "<<< Unlocking <<<");
    ReleaseWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "SecMgrSetPortParams", 986);
LABEL_11:
    v14 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_12;
  }
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v11;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 68, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, MSMSecMemory);
    goto LABEL_11;
  }
LABEL_12:
  if ( v14 != &WPP_GLOBAL_Control && (*((_DWORD *)v14 + 17) & 0x100) != 0 )
    WPP_SF_d(v14[7], 73, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x1800166b4  push    rbx
0x1800166b6  push    rbp
0x1800166b7  push    rsi
0x1800166b8  push    rdi
0x1800166b9  push    r14
0x1800166bb  push    r15
0x1800166bd  sub     rsp, 38h
0x1800166c1  mov     ebp, r9d
0x1800166c4  mov     rbx, r8
0x1800166c7  mov     rsi, rdx
0x1800166ca  mov     rdi, rcx
0x1800166cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800166d4  lea     r14, WPP_GLOBAL_Control
0x1800166db  lea     r15, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x1800166e2  cmp     rcx, r14
0x1800166e5  jnz     loc_180016875
0x1800166eb  mov     eax, [rbx]
0x1800166ed  mov     rdx, rsi; void *
0x1800166f0  mov     [rdi+12Eh], eax
0x1800166f6  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x1800166f9  movzx   eax, word ptr [rbx+4]
0x1800166fd  mov     [rdi+132h], ax
0x180016704  call    ?SecMgrSetMSMPortHandle@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEAX@Z; SecMgrSetMSMPortHandle(MSMSEC_PORT_CONTEXT *,void *)
0x180016709  lea     rsi, [rdi+1E8h]
0x180016710  mov     ecx, ebp; dwBytes
0x180016712  mov     rdx, rsi
0x180016715  call    AllocateMSMSecMemory
0x18001671a  mov     ebx, eax
0x18001671c  test    eax, eax
0x18001671e  jnz     loc_1800168C1
0x180016724  mov     rdx, [rsp+68h+Src]; Src
0x18001672c  mov     r8, rbp; Size
0x18001672f  mov     rcx, [rsi]; void *
0x180016732  call    memcpy_0
0x180016737  lea     rsi, [rdi+308h]
0x18001673e  mov     qword ptr [rdi+1F0h], 1
0x180016749  mov     rcx, rsi; struct MSMSEC_EAPOL_KEY_CACHE *
0x18001674c  call    ?FlushKeyCache@@YAXPEAUMSMSEC_EAPOL_KEY_CACHE@@@Z; FlushKeyCache(MSMSEC_EAPOL_KEY_CACHE *)
0x180016751  mov     rcx, cs:WPP_GLOBAL_Control
0x180016758  cmp     rcx, r14
0x18001675b  jz      short loc_18001676A
0x18001675d  test    dword ptr [rcx+44h], 100h
0x180016764  jnz     loc_1800168F4
0x18001676a  mov     rcx, [rdi+18h]
0x18001676e  lea     r8, aSecmgrsetportp; "SecMgrSetPortParams"
0x180016775  mov     r9d, 3C7h
0x18001677b  lea     rdx, [rcx+9D0h]
0x180016782  call    cs:__imp_AcquireWriteLock
0x180016789  nop     dword ptr [rax+rax+00h]
0x18001678e  mov     r8, [rdi+18h]
0x180016792  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x180016795  lea     rdx, [r8+0AD8h]; struct MSMSEC_HOST_DESC *
0x18001679c  mov     r8, [r8+0AE0h]; struct DOT11_MSMSEC_CONNECTION_PROFILE *
0x1800167a3  call    ?KeyMgrSetPortParams@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAUMSMSEC_HOST_DESC@@PEBUDOT11_MSMSEC_CONNECTION_PROFILE@@@Z; KeyMgrSetPortParams(MSMSEC_PORT_CONTEXT *,MSMSEC_HOST_DESC *,DOT11_MSMSEC_CONNECTION_PROFILE const *)
0x1800167a8  mov     ebx, eax
0x1800167aa  test    eax, eax
0x1800167ac  jnz     loc_180016859
0x1800167b2  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x1800167b5  call    ?AuthMgrSetPortParams@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z; AuthMgrSetPortParams(MSMSEC_PORT_CONTEXT *)
0x1800167ba  mov     ebx, eax
0x1800167bc  test    eax, eax
0x1800167be  jnz     loc_18001691E
0x1800167c4  mov     eax, [rdi+398h]
0x1800167ca  xor     edx, edx
0x1800167cc  mov     r8d, [rdi+3E8h]
0x1800167d3  dec     eax
0x1800167d5  cmp     eax, 1
0x1800167d8  mov     rcx, rsi
0x1800167db  setnbe  dl
0x1800167de  call    ?KeyCacheSetPortParams@@YAKPEAUMSMSEC_EAPOL_KEY_CACHE@@HW4KEY_EXCHANGE_TYPE@@@Z; KeyCacheSetPortParams(MSMSEC_EAPOL_KEY_CACHE *,int,KEY_EXCHANGE_TYPE)
0x1800167e3  mov     ebx, eax
0x1800167e5  test    eax, eax
0x1800167e7  jnz     loc_18001693F
0x1800167ed  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x1800167f0  call    ?WpsAuthMgrSetPortParams@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z; WpsAuthMgrSetPortParams(MSMSEC_PORT_CONTEXT *)
0x1800167f5  mov     ebx, eax
0x1800167f7  test    eax, eax
0x1800167f9  jnz     loc_180016960
0x1800167ff  mov     rcx, [rdi+18h]
0x180016803  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x18001680a  mov     ecx, [rcx+9C0h]; unsigned int
0x180016810  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180016815  mov     rcx, [rdi+18h]
0x180016819  lea     r8, aSecmgrsetportp; "SecMgrSetPortParams"
0x180016820  mov     r9d, 3DAh
0x180016826  lea     rdx, [rcx+9D0h]
0x18001682d  call    cs:__imp_ReleaseWriteLock
0x180016834  nop     dword ptr [rax+rax+00h]
0x180016839  mov     rcx, cs:WPP_GLOBAL_Control
0x180016840  cmp     rcx, r14
0x180016843  jnz     loc_180016993
0x180016849  mov     eax, ebx
0x18001684b  add     rsp, 38h
0x18001684f  pop     r15
0x180016851  pop     r14
0x180016853  pop     rdi
0x180016854  pop     rsi
0x180016855  pop     rbp
0x180016856  pop     rbx
0x180016857  retn
0x180016859  mov     rcx, cs:WPP_GLOBAL_Control
0x180016860  cmp     rcx, r14
0x180016863  jz      short loc_1800167FF
0x180016865  test    byte ptr [rcx+44h], 1
0x180016869  jz      short loc_1800167FF
0x18001686b  mov     edx, 45h ; 'E'
0x180016870  jmp     loc_18001697F
0x180016875  test    dword ptr [rcx+44h], 100h
0x18001687c  jnz     short loc_1800168A7
0x18001687e  cmp     rcx, r14
0x180016881  jz      loc_1800166EB
0x180016887  test    byte ptr [rcx+44h], 2
0x18001688b  jz      loc_1800166EB
0x180016891  mov     rcx, [rcx+38h]
0x180016895  mov     edx, 43h ; 'C'
0x18001689a  mov     r8, r15
0x18001689d  call    WPP_SF_
0x1800168a2  jmp     loc_1800166EB
0x1800168a7  mov     rcx, [rcx+38h]
0x1800168ab  mov     edx, 42h ; 'B'
0x1800168b0  mov     r8, r15
0x1800168b3  call    WPP_SF_
0x1800168b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168bf  jmp     short loc_18001687E
0x1800168c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168c8  cmp     rcx, r14
0x1800168cb  jz      loc_180016849
0x1800168d1  test    byte ptr [rcx+44h], 1
0x1800168d5  jz      loc_180016840
0x1800168db  mov     rcx, [rcx+38h]
0x1800168df  mov     edx, 44h ; 'D'
0x1800168e4  mov     r9d, eax
0x1800168e7  mov     r8, r15
0x1800168ea  call    WPP_SF_d
0x1800168ef  jmp     loc_180016839
0x1800168f4  mov     r9, [rdi+18h]
0x1800168f8  lea     rax, aLocking; ">>> Locking >>>"
0x1800168ff  mov     rcx, [rcx+38h]
0x180016903  mov     edx, 0Bh
0x180016908  mov     [rsp+68h+var_48], rax
0x18001690d  mov     r9d, [r9+9C0h]
0x180016914  call    WPP_SF_Ls
0x180016919  jmp     loc_18001676A
0x18001691e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016925  cmp     rcx, r14
0x180016928  jz      loc_1800167FF
0x18001692e  test    byte ptr [rcx+44h], 1
0x180016932  jz      loc_1800167FF
0x180016938  mov     edx, 46h ; 'F'
0x18001693d  jmp     short loc_18001697F
0x18001693f  mov     rcx, cs:WPP_GLOBAL_Control
0x180016946  cmp     rcx, r14
0x180016949  jz      loc_1800167FF
0x18001694f  test    byte ptr [rcx+44h], 1
0x180016953  jz      loc_1800167FF
0x180016959  mov     edx, 47h ; 'G'
0x18001695e  jmp     short loc_18001697F
0x180016960  mov     rcx, cs:WPP_GLOBAL_Control
0x180016967  cmp     rcx, r14
0x18001696a  jz      loc_1800167FF
0x180016970  test    byte ptr [rcx+44h], 1
0x180016974  jz      loc_1800167FF
0x18001697a  mov     edx, 48h ; 'H'
0x18001697f  mov     rcx, [rcx+38h]
0x180016983  mov     r9d, eax
0x180016986  mov     r8, r15
0x180016989  call    WPP_SF_d
0x18001698e  jmp     loc_1800167FF
0x180016993  test    dword ptr [rcx+44h], 100h
0x18001699a  jz      loc_180016849
0x1800169a0  mov     rcx, [rcx+38h]
0x1800169a4  mov     edx, 49h ; 'I'
0x1800169a9  mov     r9d, ebx
0x1800169ac  mov     r8, r15
0x1800169af  call    WPP_SF_d
0x1800169b4  jmp     loc_180016849
```
