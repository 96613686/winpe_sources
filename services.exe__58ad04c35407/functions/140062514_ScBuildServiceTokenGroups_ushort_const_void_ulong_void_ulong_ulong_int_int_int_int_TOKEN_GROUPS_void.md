# ScBuildServiceTokenGroups(ushort const *,void * *,ulong,void * *,ulong,ulong,int,int,int,int,_TOKEN_GROUPS * *,void * *)

- ea: `0x140062514`
- end: `0x1400628a0`
- name: `?ScBuildServiceTokenGroups@@YAKPEBGPEAPEAXK1KKHHHHPEAPEAU_TOKEN_GROUPS@@1@Z`
- size: `908`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, void **, unsigned int, void **, unsigned int, unsigned int, int, int, int, int, struct _TOKEN_GROUPS **, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140063928`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x140029228`
- `0x1400575b0`
- `0x140062514`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140062639`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400626bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140062639`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400626bd`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140062757`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140062757`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1400626b3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1400626b3`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x14006262d`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x14006262d`
- `ntdll!RtlAllocateHeap` at `0x140062708`
- `ntdll!RtlAllocateHeap` at `0x140062708`

## pseudocode

```c
__int64 __fastcall ScBuildServiceTokenGroups(
        const unsigned __int16 *a1,
        void **a2,
        unsigned int a3,
        void **a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        struct _TOKEN_GROUPS **a11,
        void **a12)
{
  int v12; // r14d
  DWORD LastError; // ebx
  int v17; // r15d
  unsigned int v18; // r15d
  PRPC_ASYNC_STATE v19; // rcx
  __int64 v20; // rdx
  struct _TOKEN_GROUPS *Heap; // r8
  unsigned int v22; // r9d
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 i; // r10
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  unsigned int j; // r10d
  __int64 v31; // rdx
  __int64 v32; // rax
  void **v33; // rcx
  PSID pSid; // [rsp+60h] [rbp-69h] BYREF
  struct _LUID Luid; // [rsp+68h] [rbp-61h] BYREF
  __int64 v37; // [rsp+70h] [rbp-59h]
  __int64 v38; // [rsp+78h] [rbp-51h]
  struct _TOKEN_GROUPS **v39; // [rsp+80h] [rbp-49h]
  void **v40; // [rsp+88h] [rbp-41h]
  PSID v41; // [rsp+90h] [rbp-39h]
  _DWORD v42[2]; // [rsp+98h] [rbp-31h]
  __int64 v43; // [rsp+A0h] [rbp-29h]
  int v44; // [rsp+A8h] [rbp-21h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+C0h] [rbp-9h] BYREF

  v12 = (int)a1;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v44 = 7;
  LastError = 8;
  Luid = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid = 0;
  v42[0] = (a8 != 0 ? 8 : 0) | 0xC0000007;
  v43 = LocalSid;
  v37 = WriteRestrictedSid;
  v38 = UniquifiedServiceSid;
  *a11 = 0;
  *a12 = 0;
  v39 = a11;
  v40 = a12;
  v17 = (a7 != 0) + 3;
  if ( !a10 )
    v17 = (a7 != 0) + 2;
  v18 = a5 + a3 + v17;
  if ( v18 > 0x400 )
  {
    LastError = 1389;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      return LastError;
    WPP_SF_Dd(WPP_GLOBAL_Control->StubInfo, 44, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids);
    goto LABEL_20;
  }
  if ( !AllocateLocallyUniqueId(&Luid) )
  {
    LastError = GetLastError();
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      v20 = 45;
LABEL_11:
      WPP_SF_d(v19->StubInfo, v20, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids, LastError);
      goto LABEL_20;
    }
    goto LABEL_20;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 3u, 5u, Luid.HighPart, Luid.LowPart, 0, 0, 0, 0, 0, &pSid) )
  {
    LastError = GetLastError();
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      v20 = 46;
      goto LABEL_11;
    }
LABEL_20:
    if ( pSid )
      FreeSid(pSid);
    return LastError;
  }
  v41 = pSid;
  Heap = (struct _TOKEN_GROUPS *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 16LL * (v18 - 1) + 24);
  if ( !Heap )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_Sd(WPP_GLOBAL_Control->StubInfo, 47, (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids, v12, 8);
    goto LABEL_20;
  }
  LastError = 0;
  v22 = 0;
  Heap->GroupCount = a3 + a5 + 2;
  if ( a3 )
  {
    v23 = 0;
    do
    {
      v24 = v23;
      Heap->Groups[v24].Attributes = 10;
      Heap->Groups[v24].Sid = a2[v23];
      if ( v22 == a6 || a9 && v22 == a6 + 1 )
        Heap->Groups[v23].Attributes = 14;
      ++v22;
      ++v23;
    }
    while ( v22 < a3 );
  }
  for ( i = 0; i != 2; ++i )
  {
    v26 = 2 * i;
    v27 = v22++;
    Heap->Groups[v27].Sid = *(PSID *)&v42[2 * v26 - 2];
    Heap->Groups[v27].Attributes = v42[2 * v26];
  }
  if ( a7 )
  {
    ++Heap->GroupCount;
    v28 = v22++;
    Heap->Groups[v28].Sid = (PSID)v37;
    Heap->Groups[v28].Attributes = 7;
  }
  if ( a10 )
  {
    ++Heap->GroupCount;
    v29 = v22++;
    Heap->Groups[v29].Sid = (PSID)v38;
    Heap->Groups[v29].Attributes = 7;
  }
  if ( a5 && a4 )
  {
    for ( j = 0; j < a5; ++j )
    {
      v31 = v22++;
      v31 *= 2;
      v32 = j;
      *((_QWORD *)&Heap->Groups[0].Sid + v31) = a4[v32];
      *(&Heap->Groups[0].Attributes + 2 * v31) = 7;
    }
  }
  v33 = v40;
  *v39 = Heap;
  *v33 = pSid;
  return LastError;
}

```

## disassembly

```asm
0x140062514  mov     [rsp-8+arg_8], rbx
0x140062519  push    rbp
0x14006251a  push    rsi
0x14006251b  push    rdi
0x14006251c  push    r12
0x14006251e  push    r13
0x140062520  push    r14
0x140062522  push    r15
0x140062524  lea     rbp, [rsp-7]
0x140062529  sub     rsp, 0D0h
0x140062530  mov     rax, cs:__security_cookie
0x140062537  xor     rax, rsp
0x14006253a  mov     [rbp+37h+var_38], rax
0x14006253e  mov     esi, [rbp+37h+arg_20]
0x140062541  mov     r14, rcx
0x140062544  mov     r12, r9
0x140062547  mov     word ptr [rbp+37h+pIdentifierAuthority.Value+4], 500h
0x14006254d  xor     r9d, r9d
0x140062550  mov     [rbp+37h+var_58], 7
0x140062557  neg     [rbp+37h+arg_38]
0x14006255a  mov     edi, r8d
0x14006255d  mov     r8, [rbp+37h+arg_58]
0x140062564  mov     r13, rdx
0x140062567  mov     rdx, [rbp+37h+arg_50]
0x14006256e  sbb     eax, eax
0x140062570  lea     ebx, [r9+8]
0x140062574  mov     qword ptr [rbp+37h+Luid.LowPart], r9
0x140062578  and     eax, ebx
0x14006257a  mov     dword ptr [rbp+37h+pIdentifierAuthority.Value], r9d
0x14006257e  or      eax, 0C0000007h
0x140062583  mov     [rbp+37h+var_A0], r9
0x140062587  mov     [rbp+37h+var_68], eax
0x14006258a  mov     rax, cs:LocalSid
0x140062591  mov     [rbp+37h+var_60], rax
0x140062595  mov     rax, cs:WriteRestrictedSid
0x14006259c  mov     [rbp+37h+var_90], rax
0x1400625a0  mov     rax, cs:UniquifiedServiceSid
0x1400625a7  mov     [rbp+37h+var_88], rax
0x1400625ab  mov     eax, [rbp+37h+arg_30]
0x1400625ae  neg     eax
0x1400625b0  mov     [rdx], r9
0x1400625b3  mov     [r8], r9
0x1400625b6  sbb     ecx, ecx
0x1400625b8  mov     [rbp+37h+var_80], rdx
0x1400625bc  neg     ecx
0x1400625be  mov     [rbp+37h+var_78], r8
0x1400625c2  add     ecx, 2
0x1400625c5  cmp     [rbp+37h+arg_48], r9d
0x1400625cc  mov     r9d, 400h
0x1400625d2  lea     r15d, [rcx+1]
0x1400625d6  cmovz   r15d, ecx
0x1400625da  add     r15d, edi
0x1400625dd  add     r15d, esi
0x1400625e0  cmp     r15d, r9d
0x1400625e3  jbe     short loc_140062629
0x1400625e5  mov     ebx, 56Dh
0x1400625ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400625f1  lea     rax, WPP_GLOBAL_Control
0x1400625f8  cmp     rcx, rax
0x1400625fb  jz      loc_140062877
0x140062601  test    byte ptr [rcx+1Ch], 1
0x140062605  jz      loc_140062877
0x14006260b  mov     rcx, [rcx+10h]
0x14006260f  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140062616  mov     edx, 2Ch ; ','
0x14006261b  mov     [rsp+100h+nSubAuthority2], ebx
0x14006261f  call    WPP_SF_Dd
0x140062624  jmp     loc_14006274A
0x140062629  lea     rcx, [rbp+37h+Luid]; Luid
0x14006262d  call    cs:__imp_AllocateLocallyUniqueId
0x140062633  xor     ecx, ecx
0x140062635  test    eax, eax
0x140062637  jnz     short loc_14006267F
0x140062639  call    cs:__imp_GetLastError
0x14006263f  mov     ebx, eax
0x140062641  mov     rcx, cs:WPP_GLOBAL_Control
0x140062648  lea     rax, WPP_GLOBAL_Control
0x14006264f  cmp     rcx, rax
0x140062652  jz      loc_14006274A
0x140062658  test    byte ptr [rcx+1Ch], 1
0x14006265c  jz      loc_14006274A
0x140062662  mov     edx, 2Dh ; '-'
0x140062667  mov     rcx, [rcx+10h]
0x14006266b  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140062672  mov     r9d, ebx
0x140062675  call    WPP_SF_d
0x14006267a  jmp     loc_14006274A
0x14006267f  mov     r9d, [rbp+37h+Luid.HighPart]; nSubAuthority1
0x140062683  lea     rax, [rbp+37h+var_A0]
0x140062687  mov     [rsp+100h+pSid], rax; pSid
0x14006268c  mov     r8d, 5; nSubAuthority0
0x140062692  mov     eax, [rbp+37h+Luid.LowPart]
0x140062695  mov     dl, 3; nSubAuthorityCount
0x140062697  mov     [rsp+100h+nSubAuthority7], ecx; nSubAuthority7
0x14006269b  mov     [rsp+100h+nSubAuthority6], ecx; nSubAuthority6
0x14006269f  mov     [rsp+100h+nSubAuthority5], ecx; nSubAuthority5
0x1400626a3  mov     [rsp+100h+nSubAuthority4], ecx; nSubAuthority4
0x1400626a7  mov     [rsp+100h+nSubAuthority3], ecx; nSubAuthority3
0x1400626ab  lea     rcx, [rbp+37h+pIdentifierAuthority]; pIdentifierAuthority
0x1400626af  mov     [rsp+100h+nSubAuthority2], eax; nSubAuthority2
0x1400626b3  call    cs:__imp_AllocateAndInitializeSid
0x1400626b9  test    eax, eax
0x1400626bb  jnz     short loc_1400626E5
0x1400626bd  call    cs:__imp_GetLastError
0x1400626c3  mov     ebx, eax
0x1400626c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400626cc  lea     rax, WPP_GLOBAL_Control
0x1400626d3  cmp     rcx, rax
0x1400626d6  jz      short loc_14006274A
0x1400626d8  test    byte ptr [rcx+1Ch], 1
0x1400626dc  jz      short loc_14006274A
0x1400626de  mov     edx, 2Eh ; '.'
0x1400626e3  jmp     short loc_140062667
0x1400626e5  mov     rcx, gs:60h
0x1400626ee  lea     r8d, [r15-1]
0x1400626f2  mov     rax, [rbp+37h+var_A0]
0x1400626f6  mov     edx, ebx; Flags
0x1400626f8  shl     r8, 4
0x1400626fc  add     r8, 18h; Size
0x140062700  mov     [rbp+37h+var_70], rax
0x140062704  mov     rcx, [rcx+30h]; HeapHandle
0x140062708  call    cs:__imp_RtlAllocateHeap
0x14006270e  mov     r8, rax
0x140062711  test    rax, rax
0x140062714  jnz     short loc_140062762
0x140062716  mov     rcx, cs:WPP_GLOBAL_Control
0x14006271d  lea     rax, WPP_GLOBAL_Control
0x140062724  cmp     rcx, rax
0x140062727  jz      short loc_14006274A
0x140062729  test    byte ptr [rcx+1Ch], 1
0x14006272d  jz      short loc_14006274A
0x14006272f  mov     rcx, [rcx+10h]
0x140062733  lea     edx, [r8+2Fh]
0x140062737  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x14006273e  mov     [rsp+100h+nSubAuthority2], ebx
0x140062742  mov     r9, r14
0x140062745  call    WPP_SF_Sd
0x14006274a  mov     rcx, [rbp+37h+var_A0]; pSid
0x14006274e  test    rcx, rcx
0x140062751  jz      loc_140062877
0x140062757  call    cs:__imp_FreeSid
0x14006275d  jmp     loc_140062877
0x140062762  xor     ebx, ebx
0x140062764  lea     eax, [rsi+2]
0x140062767  add     eax, edi
0x140062769  mov     r9d, ebx
0x14006276c  mov     [r8], eax
0x14006276f  test    edi, edi
0x140062771  jz      short loc_1400627BC
0x140062773  mov     r10d, [rbp+37h+arg_28]
0x140062777  mov     edx, ebx
0x140062779  mov     rcx, rdx
0x14006277c  add     rcx, rcx
0x14006277f  mov     dword ptr [r8+rcx*8+10h], 0Ah
0x140062788  mov     rax, [r13+rdx*8+0]
0x14006278d  mov     [r8+rcx*8+8], rax
0x140062792  cmp     r9d, r10d
0x140062795  jz      short loc_1400627A8
0x140062797  cmp     [rbp+37h+arg_40], ebx
0x14006279d  jz      short loc_1400627B1
0x14006279f  lea     eax, [r10+1]
0x1400627a3  cmp     r9d, eax
0x1400627a6  jnz     short loc_1400627B1
0x1400627a8  mov     dword ptr [r8+rcx*8+10h], 0Eh
0x1400627b1  inc     r9d
0x1400627b4  inc     rdx
0x1400627b7  cmp     r9d, edi
0x1400627ba  jb      short loc_140062779
0x1400627bc  mov     r10, rbx
0x1400627bf  mov     rdx, r10
0x1400627c2  mov     ecx, r9d
0x1400627c5  add     rdx, rdx
0x1400627c8  add     rcx, rcx
0x1400627cb  inc     r9d
0x1400627ce  inc     r10
0x1400627d1  mov     rax, [rbp+rdx*8+37h+var_70]
0x1400627d6  mov     [r8+rcx*8+8], rax
0x1400627db  mov     eax, [rbp+rdx*8+37h+var_68]
0x1400627df  mov     [r8+rcx*8+10h], eax
0x1400627e4  cmp     r10, 2
0x1400627e8  jnz     short loc_1400627BF
0x1400627ea  cmp     [rbp+37h+arg_30], ebx
0x1400627ed  jz      short loc_14006280D
0x1400627ef  inc     dword ptr [r8]
0x1400627f2  mov     rcx, [rbp+37h+var_90]
0x1400627f6  mov     eax, r9d
0x1400627f9  add     rax, rax
0x1400627fc  inc     r9d
0x1400627ff  mov     [r8+rax*8+8], rcx
0x140062804  mov     dword ptr [r8+rax*8+10h], 7
0x14006280d  cmp     [rbp+37h+arg_48], ebx
0x140062813  jz      short loc_140062833
0x140062815  inc     dword ptr [r8]
0x140062818  mov     rcx, [rbp+37h+var_88]
0x14006281c  mov     eax, r9d
0x14006281f  add     rax, rax
0x140062822  inc     r9d
0x140062825  mov     [r8+rax*8+8], rcx
0x14006282a  mov     dword ptr [r8+rax*8+10h], 7
0x140062833  test    esi, esi
0x140062835  jz      short loc_140062865
0x140062837  test    r12, r12
0x14006283a  jz      short loc_140062865
0x14006283c  mov     r10d, ebx
0x14006283f  mov     edx, r9d
0x140062842  inc     r9d
0x140062845  add     rdx, rdx
0x140062848  mov     eax, r10d
0x14006284b  inc     r10d
0x14006284e  mov     rcx, [r12+rax*8]
0x140062852  mov     [r8+rdx*8+8], rcx
0x140062857  mov     dword ptr [r8+rdx*8+10h], 7
0x140062860  cmp     r10d, esi
0x140062863  jb      short loc_14006283F
0x140062865  mov     rax, [rbp+37h+var_80]
0x140062869  mov     rcx, [rbp+37h+var_78]
0x14006286d  mov     [rax], r8
0x140062870  mov     rax, [rbp+37h+var_A0]
0x140062874  mov     [rcx], rax
0x140062877  mov     eax, ebx
0x140062879  mov     rcx, [rbp+37h+var_38]
0x14006287d  xor     rcx, rsp; StackCookie
0x140062880  call    __security_check_cookie
0x140062885  mov     rbx, [rsp+100h+arg_8]
0x14006288d  add     rsp, 0D0h
0x140062894  pop     r15
0x140062896  pop     r14
0x140062898  pop     r13
0x14006289a  pop     r12
0x14006289c  pop     rdi
0x14006289d  pop     rsi
0x14006289e  pop     rbp
0x14006289f  retn
```
