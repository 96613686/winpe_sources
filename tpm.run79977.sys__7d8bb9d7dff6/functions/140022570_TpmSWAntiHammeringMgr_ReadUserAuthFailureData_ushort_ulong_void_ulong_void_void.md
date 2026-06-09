# TpmSWAntiHammeringMgr::_ReadUserAuthFailureData(ushort *,ulong,void *,ulong,void *,void *)

- ea: `0x140022570`
- end: `0x1400227e4`
- name: `?_ReadUserAuthFailureData@TpmSWAntiHammeringMgr@@CAJPEAGKPEAXK11@Z`
- size: `628`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, void *, unsigned int, void *, void *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task`

## callees

- `0x1400052f0`
- `0x14000b9a4`
- `0x14000e854`
- `0x140010eb8`
- `0x14001ac60`
- `0x140022138`
- `0x140022570`
- `0x140028ef0`
- `0x14003005c`
- `0x140030218`
- `0x140039718`
- `0x140039740`
- `0x140045430`
- `0x1400454a0`

## string_xrefs

- `0x1400225f1`: `\Registry\Machine\System\CurrentControlSet\Services\TPM\AuthorizationFailure`

## pseudocode

```c
__int64 __fastcall TpmSWAntiHammeringMgr::_ReadUserAuthFailureData(
        unsigned __int16 *a1,
        __int64 a2,
        void *a3,
        __int64 a4,
        unsigned int *a5)
{
  STRSAFE_PCNZWCH v5; // r11
  NTSTATUS v6; // ebx
  int v7; // edx
  unsigned __int8 *v8; // rsi
  unsigned int v9; // edi
  unsigned __int64 v10; // rcx
  unsigned int *v11; // rax
  unsigned int *v12; // rdi
  int v13; // eax
  unsigned int *v14; // r8
  unsigned int v15; // edx
  unsigned int v16; // eax
  unsigned int v17; // ebx
  void *v18; // rcx
  rsize_t v19; // rdx
  void **v20; // r8
  unsigned int v22; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v23; // [rsp+34h] [rbp-CCh] BYREF
  size_t pcchLength; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t pszDest[256]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t v26[336]; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int64 retaddr; // [rsp+508h] [rbp+408h]

  v22 = 0;
  v23 = 0;
  pcchLength = 0;
  RtlStringCchLengthW(a1, 0x104u, &pcchLength);
  RtlStringCchCopyNW(pszDest, 0x100u, v5, pcchLength);
  v6 = RtlStringCchPrintfW(
         v26,
         0x14Eu,
         L"%s\\%s",
         L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\TPM\\AuthorizationFailure",
         pszDest);
  if ( v6 >= 0 )
  {
    v6 = TpmRegistry::QueryValue(v26, L"Count", 4u, &v22, 4u, 0);
    if ( v6 >= 0 )
    {
      if ( v22 <= 0x64 )
      {
        v9 = 8 * v22;
        v8 = TpmAlloc(1, 8 * v22, retaddr);
        if ( !v8 )
          return (unsigned int)-1073741670;
        v6 = TpmRegistry::QueryValue(v26, L"History", 3u, v8, v9, &v23);
        if ( v6 < 0 )
        {
LABEL_23:
          TpmFree(v8);
          return (unsigned int)v6;
        }
        if ( v23 == v9 )
        {
          v11 = (unsigned int *)TpmUserAuthFailureData::operator new(v10);
          v12 = v11;
          if ( v11 )
          {
            *(_QWORD *)v11 = 0;
            *((_QWORD *)v11 + 1) = 0;
            *((_QWORD *)v11 + 2) = 0;
            *((_QWORD *)v11 + 4) = v11 + 6;
            *((_QWORD *)v11 + 3) = v11 + 6;
            v13 = wcscmp_0(pszDest, L"ALLSTANDARDUSERS");
            v14 = a5 + 1;
            if ( v13 )
              v14 = a5;
            v6 = TpmUserAuthFailureData::Initialize((TpmUserAuthFailureData *)v12, pszDest, *v14);
            if ( v6 < 0 )
            {
              TpmRequest::`scalar deleting destructor'((TpmRequest *)v12, v15);
            }
            else
            {
              v16 = v12[4];
              v17 = v22;
              v18 = (void *)*((_QWORD *)v12 + 1);
              v19 = 8LL * v16;
              if ( v22 > v16 )
              {
                memcpy_s(v18, v19, &v8[8 * (v22 - v16)], 8LL * v12[4]);
                v17 = v12[4];
              }
              else
              {
                memcpy_s(v18, v19, v8, 8LL * v22);
              }
              v12[5] = v17;
              v20 = (void **)*((_QWORD *)a5 + 3);
              if ( *v20 != a5 + 4 )
                __fastfail(3u);
              v6 = 0;
              *((_QWORD *)v12 + 3) = a5 + 4;
              *((_QWORD *)v12 + 4) = v20;
              *v20 = v12 + 6;
              *((_QWORD *)a5 + 3) = v12 + 6;
            }
          }
          else
          {
            v6 = -1073741670;
          }
          goto LABEL_23;
        }
      }
      else
      {
        v8 = 0;
      }
      v6 = -1073741820;
      TpmRegistry::DeleteKey(v26, v7);
      if ( v8 )
        goto LABEL_23;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140022570  mov     [rsp-8+arg_8], rbx
0x140022575  mov     [rsp-8+arg_10], rsi
0x14002257a  push    rbp
0x14002257b  push    rdi
0x14002257c  push    r14
0x14002257e  lea     rbp, [rsp-3F0h]
0x140022586  sub     rsp, 4F0h
0x14002258d  mov     rax, cs:__security_cookie
0x140022594  xor     rax, rsp
0x140022597  mov     [rbp+400h+var_20], rax
0x14002259e  mov     r14, [rbp+400h+arg_20]
0x1400225a5  lea     r8, [rsp+500h+pcchLength]; pcchLength
0x1400225aa  mov     edx, 104h; cchMax
0x1400225af  mov     [rsp+500h+var_4D0], 0
0x1400225b7  mov     r11, rcx
0x1400225ba  mov     [rsp+500h+var_4CC], 0
0x1400225c2  mov     [rsp+500h+pcchLength], 0
0x1400225cb  call    RtlStringCchLengthW
0x1400225d0  mov     r9, [rsp+500h+pcchLength]; cchToCopy
0x1400225d5  lea     rcx, [rsp+500h+pszDest]; pszDest
0x1400225da  mov     edx, 100h; cchDest
0x1400225df  mov     r8, r11; pszSrc
0x1400225e2  call    RtlStringCchCopyNW
0x1400225e7  lea     r10, [rsp+500h+pszDest]
0x1400225ec  mov     edx, 14Eh; cchDest
0x1400225f1  lea     r9, aRegistryMachin_18; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400225f8  mov     qword ptr [rsp+500h+var_4E0], r10
0x1400225fd  lea     r8, aSS; "%s\\%s"
0x140022604  lea     rcx, [rbp+400h+var_2C0]; pszDest
0x14002260b  call    RtlStringCchPrintfW
0x140022610  mov     ebx, eax
0x140022612  test    eax, eax
0x140022614  js      loc_1400227BA
0x14002261a  mov     r8d, 4; unsigned int
0x140022620  mov     [rsp+500h+var_4D8], 0; unsigned int *
0x140022629  lea     r9, [rsp+500h+var_4D0]; void *
0x14002262e  mov     [rsp+500h+var_4E0], r8d; unsigned int
0x140022633  lea     rdx, aCount; "Count"
0x14002263a  lea     rcx, [rbp+400h+var_2C0]; unsigned __int16 *
0x140022641  call    ?QueryValue@TpmRegistry@@SAJPEBG0KPEAXKPEAK@Z; TpmRegistry::QueryValue(ushort const *,ushort const *,ulong,void *,ulong,ulong *)
0x140022646  mov     ebx, eax
0x140022648  test    eax, eax
0x14002264a  js      loc_1400227BA
0x140022650  mov     edi, [rsp+500h+var_4D0]
0x140022654  cmp     edi, 64h ; 'd'
0x140022657  jbe     short loc_14002265D
0x140022659  xor     esi, esi
0x14002265b  jmp     short loc_1400226BC
0x14002265d  mov     r8, [rbp+408h]; unsigned __int64
0x140022664  mov     cl, 1; bool
0x140022666  shl     edi, 3
0x140022669  mov     edx, edi; unsigned __int64
0x14002266b  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x140022670  mov     rsi, rax
0x140022673  test    rax, rax
0x140022676  jnz     short loc_140022682
0x140022678  mov     ebx, 0C000009Ah
0x14002267d  jmp     loc_1400227BA
0x140022682  lea     rax, [rsp+500h+var_4CC]
0x140022687  mov     r9, rsi; void *
0x14002268a  mov     [rsp+500h+var_4D8], rax; unsigned int *
0x14002268f  lea     rdx, aHistory; "History"
0x140022696  mov     r8d, 3; unsigned int
0x14002269c  mov     [rsp+500h+var_4E0], edi; unsigned int
0x1400226a0  lea     rcx, [rbp+400h+var_2C0]; unsigned __int16 *
0x1400226a7  call    ?QueryValue@TpmRegistry@@SAJPEBG0KPEAXKPEAK@Z; TpmRegistry::QueryValue(ushort const *,ushort const *,ulong,void *,ulong,ulong *)
0x1400226ac  mov     ebx, eax
0x1400226ae  test    eax, eax
0x1400226b0  js      loc_1400227B2
0x1400226b6  cmp     [rsp+500h+var_4CC], edi
0x1400226ba  jz      short loc_1400226DB
0x1400226bc  lea     rcx, [rbp+400h+var_2C0]; unsigned __int16 *
0x1400226c3  mov     ebx, 0C0000004h
0x1400226c8  call    ?DeleteKey@TpmRegistry@@SAJPEBGH@Z; TpmRegistry::DeleteKey(ushort const *,int)
0x1400226cd  test    rsi, rsi
0x1400226d0  jz      loc_1400227BA
0x1400226d6  jmp     loc_1400227B2
0x1400226db  call    ??2TpmUserAuthFailureData@@SAPEAX_K@Z; TpmUserAuthFailureData::operator new(unsigned __int64)
0x1400226e0  mov     rdi, rax
0x1400226e3  test    rax, rax
0x1400226e6  jz      loc_1400227AD
0x1400226ec  lea     rcx, [rax+18h]
0x1400226f0  mov     qword ptr [rax], 0
0x1400226f7  mov     qword ptr [rax+8], 0
0x1400226ff  lea     rdx, aAllstandarduse; "ALLSTANDARDUSERS"
0x140022706  mov     qword ptr [rax+10h], 0
0x14002270e  mov     [rcx+8], rcx
0x140022712  mov     [rcx], rcx
0x140022715  lea     rcx, [rsp+500h+pszDest]; Str1
0x14002271a  call    wcscmp_0
0x14002271f  test    eax, eax
0x140022721  lea     r8, [r14+4]
0x140022725  lea     rdx, [rsp+500h+pszDest]; unsigned __int16 *
0x14002272a  mov     rcx, rdi; this
0x14002272d  cmovnz  r8, r14
0x140022731  mov     r8d, [r8]; unsigned int
0x140022734  call    ?Initialize@TpmUserAuthFailureData@@QEAAJPEBGK@Z; TpmUserAuthFailureData::Initialize(ushort const *,ulong)
0x140022739  mov     ebx, eax
0x14002273b  test    eax, eax
0x14002273d  js      short loc_1400227A3
0x14002273f  mov     eax, [rdi+10h]
0x140022742  mov     ebx, [rsp+500h+var_4D0]
0x140022746  mov     edx, eax
0x140022748  mov     rcx, [rdi+8]; void *
0x14002274c  shl     rdx, 3; DstSize
0x140022750  cmp     ebx, eax
0x140022752  ja      short loc_140022765
0x140022754  mov     r9d, ebx
0x140022757  mov     r8, rsi; Src
0x14002275a  shl     r9, 3; MaxCount
0x14002275e  call    memcpy_s
0x140022763  jmp     short loc_140022776
0x140022765  sub     ebx, eax
0x140022767  mov     r9, rdx; MaxCount
0x14002276a  lea     r8, [rsi+rbx*8]; Src
0x14002276e  call    memcpy_s
0x140022773  mov     ebx, [rdi+10h]
0x140022776  lea     rdx, [r14+10h]
0x14002277a  mov     [rdi+14h], ebx
0x14002277d  mov     r8, [rdx+8]
0x140022781  cmp     [r8], rdx
0x140022784  jz      short loc_14002278D
0x140022786  mov     ecx, 3
0x14002278b  int     29h; Win8: RtlFailFast(ecx)
0x14002278d  lea     rax, [rdi+18h]
0x140022791  xor     ebx, ebx
0x140022793  mov     [rax], rdx
0x140022796  mov     [rax+8], r8
0x14002279a  mov     [r8], rax
0x14002279d  mov     [rdx+8], rax
0x1400227a1  jmp     short loc_1400227B2
0x1400227a3  mov     rcx, rdi; this
0x1400227a6  call    ??_GTpmRequest@@QEAAPEAXI@Z; TpmRequest::`scalar deleting destructor'(uint)
0x1400227ab  jmp     short loc_1400227B2
0x1400227ad  mov     ebx, 0C000009Ah
0x1400227b2  mov     rcx, rsi; void *
0x1400227b5  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x1400227ba  mov     eax, ebx
0x1400227bc  mov     rcx, [rbp+400h+var_20]
0x1400227c3  xor     rcx, rsp; StackCookie
0x1400227c6  call    __security_check_cookie
0x1400227cb  lea     r11, [rsp+500h+var_10]
0x1400227d3  mov     rbx, [r11+28h]
0x1400227d7  mov     rsi, [r11+30h]
0x1400227db  mov     rsp, r11
0x1400227de  pop     r14
0x1400227e0  pop     rdi
0x1400227e1  pop     rbp
0x1400227e2  retn
```
