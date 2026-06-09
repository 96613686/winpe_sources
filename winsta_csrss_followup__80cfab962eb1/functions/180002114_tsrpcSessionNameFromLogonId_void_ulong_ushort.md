# _tsrpcSessionNameFromLogonId(void *,ulong,ushort *)

- ea: `0x180002114`
- end: `0x18000245c`
- name: `?_tsrpcSessionNameFromLogonId@@YAJPEAXKPEAG@Z`
- size: `840`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000a670`
- `0x180021fa4`

## callees

- `0x180002014`
- `0x180002114`
- `0x1800041a0`
- `0x1800045d0`
- `0x180005280`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x180032be6`
- `0x180032c20`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023b9`
- `RPCRT4!I_RpcExceptionFilter` at `0x180032e09`
- `RPCRT4!I_RpcExceptionFilter` at `0x180032e09`
- `RPCRT4!NdrClientCall3` at `0x1800022dd`
- `RPCRT4!NdrClientCall3` at `0x1800022dd`

## string_xrefs

- `0x1800023d4`: `_tsrpcSessionNameFromLogonId: Failed to open LSM binding`
- `0x180002446`: `Session::Open failed: 0x%x in %s`
- `0x180002429`: `_tsrpcSessionNameFromLogonId: Failed to open RCM binding`

## pseudocode

```c
__int64 __fastcall _tsrpcSessionNameFromLogonId(void *a1, unsigned int a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // rsi
  CLIENT_CALL_RETURN v6; // rbx
  void *v7; // rax
  int v8; // eax
  int TerminalName; // eax
  __int64 v11; // rax
  unsigned int v12; // edx
  HLOCAL v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rax
  unsigned __int16 *v16; // r9
  __int64 v17; // rcx
  unsigned __int16 v18; // r10
  unsigned __int16 *v19; // rax
  _DWORD v20[4]; // [rsp+40h] [rbp-198h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-188h] BYREF
  unsigned __int16 v22[8]; // [rsp+58h] [rbp-180h] BYREF
  CLIENT_CALL_RETURN v23; // [rsp+68h] [rbp-170h]
  unsigned __int16 *v24; // [rsp+70h] [rbp-168h]
  unsigned __int16 v25[12]; // [rsp+78h] [rbp-160h] BYREF
  __int64 v26; // [rsp+90h] [rbp-148h] BYREF
  int v27; // [rsp+98h] [rbp-140h]
  __int128 v28; // [rsp+A0h] [rbp-138h]
  __int128 v29; // [rsp+B0h] [rbp-128h]
  __int128 v30; // [rsp+C0h] [rbp-118h]
  __int64 v31; // [rsp+D0h] [rbp-108h]
  _QWORD v32[27]; // [rsp+D8h] [rbp-100h] BYREF

  v3 = a3;
  v20[2] = a2;
  v24 = a3;
  LODWORD(v6.Pointer) = -2147024882;
  v26 = 0;
  v27 = -1;
  v32[26] = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  memset_0(v32, 0, 0xD0u);
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v25, a1, 0);
  if ( CSmartPublicBinding::operator void *(v25) )
  {
    if ( a2 == -1 )
    {
      _DbgPrintMessage(8, "_tsrpcSessionNameFromLogonId - LogonId is LOGONID_CURRENT - UNEXPECTED!!");
      LODWORD(v6.Pointer) = -2147467259;
    }
    else if ( a2 >= 0x10000 )
    {
      CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v22, a1, 1);
      hMem = 0;
      v20[0] = 0;
      if ( CSmartPublicBinding::operator void *(v22) )
      {
        v11 = CSmartPublicBinding::operator void *(v22);
        v23.Simple = 0;
        v6.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035078, 8u, 0, v11, &hMem, 1, v20).Pointer;
        v23.Pointer = v6.Pointer;
        v20[1] = v6.Pointer;
        if ( SLODWORD(v6.Simple) < 0 )
        {
          _DbgPrintMessage(
            8,
            "RcpGetAllListeners failed: 0x%x in %s",
            LODWORD(v6.Pointer),
            "_tsrpcSessionNameFromLogonId");
        }
        else
        {
          v12 = 0;
          v13 = hMem;
          while ( v12 < v20[0] )
          {
            v14 = 80LL * v12;
            if ( *(_DWORD *)((char *)hMem + v14 + 4) == a2 )
            {
              v15 = 2147483646;
              v16 = (unsigned __int16 *)((char *)hMem + v14 + 12);
              v17 = 32;
              do
              {
                if ( !v15 )
                  break;
                v18 = *v16;
                if ( !*v16 )
                  break;
                ++v16;
                *v3++ = v18;
                --v15;
                --v17;
              }
              while ( v17 );
              v19 = v3 - 1;
              if ( v17 )
                v19 = v3;
              *v19 = 0;
              LODWORD(v6.Pointer) = v17 == 0 ? 0x8007007A : 0;
              break;
            }
            ++v12;
          }
          if ( v12 == v20[0] )
            LODWORD(v6.Pointer) = -2147017874;
          if ( v13 )
            LocalFree(v13);
        }
      }
      else
      {
        _DbgPrintMessage(8, "_tsrpcSessionNameFromLogonId: Failed to open RCM binding");
      }
      CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v22);
    }
    else
    {
      v7 = (void *)CSmartPublicBinding::operator void *(v25);
      v8 = CSmartSession::Open((CSmartSession *)&v26, a2, v7);
      if ( v8 == -2147024894 )
        v8 = -2147017874;
      LODWORD(v6.Pointer) = v8;
      if ( v8 < 0 )
      {
        _DbgPrintMessage(8, "Session::Open failed: 0x%x in %s", v8, "_tsrpcSessionNameFromLogonId");
      }
      else
      {
        TerminalName = CSmartSession::GetTerminalName((CSmartSession *)&v26, v3);
        if ( TerminalName == -2147024891 )
          TerminalName = -2147017874;
        LODWORD(v6.Pointer) = TerminalName;
      }
    }
  }
  else
  {
    _DbgPrintMessage(8, "_tsrpcSessionNameFromLogonId: Failed to open LSM binding");
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v25);
  CSmartSession::~CSmartSession((CSmartSession *)&v26);
  return LODWORD(v6.Pointer);
}

```

## disassembly

```asm
0x180002114  mov     r11, rsp
0x180002117  mov     [r11+8], rbx
0x18000211b  mov     [r11+20h], rsi
0x18000211f  push    rdi
0x180002120  push    r14
0x180002122  push    r15
0x180002124  sub     rsp, 1C0h
0x18000212b  mov     rax, cs:__security_cookie
0x180002132  xor     rax, rsp
0x180002135  mov     [rsp+1D8h+var_28], rax
0x18000213d  mov     rsi, r8
0x180002140  mov     r14d, edx
0x180002143  mov     r15, rcx
0x180002146  mov     [rsp+1D8h+var_190], edx
0x18000214a  mov     [rsp+1D8h+var_168], r8
0x18000214f  mov     ebx, 8007000Eh
0x180002154  xor     edi, edi
0x180002156  mov     [r11-148h], rdi
0x18000215d  mov     [rsp+1D8h+var_140], 0FFFFFFFFh
0x180002168  mov     [r11-30h], rdi
0x18000216c  xorps   xmm0, xmm0
0x18000216f  xor     eax, eax
0x180002171  movups  [rsp+1D8h+var_138], xmm0
0x180002179  movups  [rsp+1D8h+var_128], xmm0
0x180002181  movups  [rsp+1D8h+var_118], xmm0
0x180002189  mov     [r11-108h], rax
0x180002190  xor     edx, edx; Val
0x180002192  mov     r8d, 0D0h; Size
0x180002198  lea     rcx, [r11-100h]; void *
0x18000219f  call    memset_0
0x1800021a4  xor     r8d, r8d; int
0x1800021a7  mov     rdx, r15; void *
0x1800021aa  lea     rcx, [rsp+1D8h+var_160]; this
0x1800021af  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x1800021b4  lea     rcx, [rsp+1D8h+var_160]; unsigned __int16 *
0x1800021b9  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800021be  test    rax, rax
0x1800021c1  jz      loc_1800023D4
0x1800021c7  cmp     r14d, 0FFFFFFFFh
0x1800021cb  jz      loc_18000240E
0x1800021d1  cmp     r14d, 10000h
0x1800021d8  jnb     loc_180002272
0x1800021de  lea     rcx, [rsp+1D8h+var_160]; unsigned __int16 *
0x1800021e3  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800021e8  mov     r8, rax; void *
0x1800021eb  mov     edx, r14d; unsigned int
0x1800021ee  lea     rcx, [rsp+1D8h+var_148]; this
0x1800021f6  call    ?Open@CSmartSession@@QEAAJKPEAX@Z; CSmartSession::Open(ulong,void *)
0x1800021fb  mov     r14d, 80071B6Eh
0x180002201  cmp     eax, 80070002h
0x180002206  cmovz   eax, r14d
0x18000220a  mov     ebx, eax
0x18000220c  test    eax, eax
0x18000220e  js      loc_18000243C
0x180002214  mov     rdx, rsi; unsigned __int16 *
0x180002217  lea     rcx, [rsp+1D8h+var_148]; this
0x18000221f  call    ?GetTerminalName@CSmartSession@@QEAAJPEAG@Z; CSmartSession::GetTerminalName(ushort *)
0x180002224  cmp     eax, 80070005h
0x180002229  cmovz   eax, r14d
0x18000222d  mov     ebx, eax
0x18000222f  lea     rcx, [rsp+1D8h+var_160]; this
0x180002234  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180002239  lea     rcx, [rsp+1D8h+var_148]; this
0x180002241  call    ??1CSmartSession@@QEAA@XZ; CSmartSession::~CSmartSession(void)
0x180002246  mov     eax, ebx
0x180002248  mov     rcx, [rsp+1D8h+var_28]
0x180002250  xor     rcx, rsp; StackCookie
0x180002253  call    __security_check_cookie
0x180002258  lea     r11, [rsp+1D8h+var_18]
0x180002260  mov     rbx, [r11+20h]
0x180002264  mov     rsi, [r11+38h]
0x180002268  mov     rsp, r11
0x18000226b  pop     r15
0x18000226d  pop     r14
0x18000226f  pop     rdi
0x180002270  retn
0x180002272  mov     r8d, 1; int
0x180002278  mov     rdx, r15; void *
0x18000227b  lea     rcx, [rsp+1D8h+var_180]; this
0x180002280  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180002285  mov     [rsp+1D8h+hMem], rdi
0x18000228a  mov     [rsp+1D8h+var_198], edi
0x18000228e  lea     rcx, [rsp+1D8h+var_180]; unsigned __int16 *
0x180002293  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180002298  test    rax, rax
0x18000229b  jz      loc_180002429
0x1800022a1  lea     rcx, [rsp+1D8h+var_180]; unsigned __int16 *
0x1800022a6  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800022ab  mov     [rsp+1D8h+var_170], rdi
0x1800022b0  lea     rcx, [rsp+1D8h+var_198]
0x1800022b5  mov     [rsp+1D8h+var_1A8], rcx
0x1800022ba  mov     [rsp+1D8h+var_1B0], 1
0x1800022c2  lea     rcx, [rsp+1D8h+hMem]
0x1800022c7  mov     [rsp+1D8h+var_1B8], rcx
0x1800022cc  mov     r9, rax
0x1800022cf  xor     r8d, r8d; pReturnValue
0x1800022d2  lea     edx, [r8+8]; nProcNum
0x1800022d6  lea     rcx, stru_180035078; pProxyInfo
0x1800022dd  call    cs:__imp_NdrClientCall3
0x1800022e4  nop     dword ptr [rax+rax+00h]
0x1800022e9  mov     rbx, rax
0x1800022ec  mov     [rsp+1D8h+var_170], rax
0x1800022f1  mov     [rsp+1D8h+var_194], eax
0x1800022f5  jmp     short loc_180002329
0x1800022f7  test    eax, eax
0x1800022f9  jle     short loc_180002303
0x1800022fb  movzx   eax, ax
0x1800022fe  or      eax, 80070000h
0x180002303  mov     ebx, eax
0x180002305  mov     [rsp+1D8h+var_194], eax
0x180002309  mov     r8d, eax
0x18000230c  lea     rdx, aRcpgetallliste; "RcpGetAllListeners threw an exception: "...
0x180002313  mov     ecx, 8; int
0x180002318  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000231d  xor     edi, edi
0x18000231f  mov     r14d, [rsp+1D8h+var_190]
0x180002324  mov     rsi, [rsp+1D8h+var_168]
0x180002329  test    ebx, ebx
0x18000232b  js      loc_1800023EA
0x180002331  mov     edx, edi
0x180002333  mov     r8, [rsp+1D8h+hMem]
0x180002338  cmp     edx, [rsp+1D8h+var_198]
0x18000233c  jnb     short loc_1800023A3
0x18000233e  mov     eax, edx
0x180002340  lea     rcx, [rax+rax*4]
0x180002344  shl     rcx, 4
0x180002348  cmp     [rcx+r8+4], r14d
0x18000234d  jnz     loc_180002407
0x180002353  mov     eax, 7FFFFFFEh
0x180002358  lea     r9, [r8+0Ch]
0x18000235c  add     r9, rcx
0x18000235f  mov     ecx, 20h ; ' '
0x180002364  test    rax, rax
0x180002367  jz      short loc_180002388
0x180002369  movzx   r10d, word ptr [r9]
0x18000236d  test    r10w, r10w
0x180002371  jz      short loc_180002388
0x180002373  add     r9, 2
0x180002377  mov     [rsi], r10w
0x18000237b  add     rsi, 2
0x18000237f  dec     rax
0x180002382  sub     rcx, 1
0x180002386  jnz     short loc_180002364
0x180002388  lea     rax, [rsi-2]
0x18000238c  test    rcx, rcx
0x18000238f  cmovnz  rax, rsi
0x180002393  mov     [rax], di
0x180002396  neg     rcx
0x180002399  sbb     ebx, ebx
0x18000239b  not     ebx
0x18000239d  and     ebx, 8007007Ah
0x1800023a3  mov     r14d, 80071B6Eh
0x1800023a9  cmp     edx, [rsp+1D8h+var_198]
0x1800023ad  cmovz   ebx, r14d
0x1800023b1  test    r8, r8
0x1800023b4  jz      short loc_1800023C5
0x1800023b6  mov     rcx, r8; hMem
0x1800023b9  call    cs:__imp_LocalFree
0x1800023c0  nop     dword ptr [rax+rax+00h]
0x1800023c5  lea     rcx, [rsp+1D8h+var_180]; this
0x1800023ca  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x1800023cf  jmp     loc_18000222F
0x1800023d4  lea     rdx, aTsrpcsessionna; "_tsrpcSessionNameFromLogonId: Failed to"...
0x1800023db  mov     ecx, 8; int
0x1800023e0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800023e5  jmp     loc_18000222F
0x1800023ea  lea     r9, aTsrpcsessionna_2; "_tsrpcSessionNameFromLogonId"
0x1800023f1  mov     r8d, ebx
0x1800023f4  lea     rdx, aRcpgetallliste_0; "RcpGetAllListeners failed: 0x%x in %s"
0x1800023fb  mov     ecx, 8; int
0x180002400  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002405  jmp     short loc_1800023C5
0x180002407  inc     edx
0x180002409  jmp     loc_180002338
0x18000240e  lea     rdx, aTsrpcsessionna_1; "_tsrpcSessionNameFromLogonId - LogonId "...
0x180002415  mov     ecx, 8; int
0x18000241a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000241f  mov     ebx, 80004005h
0x180002424  jmp     loc_18000222F
0x180002429  lea     rdx, aTsrpcsessionna_3; "_tsrpcSessionNameFromLogonId: Failed to"...
0x180002430  mov     ecx, 8; int
0x180002435  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000243a  jmp     short loc_1800023C5
0x18000243c  lea     r9, aTsrpcsessionna_2; "_tsrpcSessionNameFromLogonId"
0x180002443  mov     r8d, eax
0x180002446  lea     rdx, aSessionOpenFai_0; "Session::Open failed: 0x%x in %s"
0x18000244d  mov     ecx, 8; int
0x180002452  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002457  jmp     loc_18000222F
0x180032dfb  push    rbp
0x180032dfd  sub     rsp, 40h
0x180032e01  mov     rbp, rdx
0x180032e04  mov     rcx, [rcx]
0x180032e07  mov     ecx, [rcx]; ExceptionCode
0x180032e09  call    cs:__imp_I_RpcExceptionFilter
0x180032e10  nop     dword ptr [rax+rax+00h]
0x180032e15  nop
0x180032e16  add     rsp, 40h
0x180032e1a  pop     rbp
0x180032e1b  retn
```
