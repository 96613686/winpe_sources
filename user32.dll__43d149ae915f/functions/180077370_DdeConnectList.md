# DdeConnectList

- ea: `0x180077370`
- end: `0x18007763a`
- name: `DdeConnectList`
- size: `714`
- prototype: `HCONVLIST __stdcall(DWORD idInst, HSZ hszService, HSZ hszTopic, HCONVLIST hConvList, PCONVCONTEXT pCC)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callees

- `0x18000bd00`
- `0x180046604`
- `0x180046dec`
- `0x180048320`
- `0x18005e2b4`
- `0x180076dd0`
- `0x180077108`
- `0x180077370`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x1800773af`
- `ntdll!RtlEnterCriticalSection` at `0x1800773af`
- `ntdll!RtlLeaveCriticalSection` at `0x180077619`
- `ntdll!RtlLeaveCriticalSection` at `0x180077619`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007745f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007745f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800774a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800774a7`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800774f3`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800774f3`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18007760c`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18007760c`

## pseudocode

```c
HCONVLIST __stdcall DdeConnectList(DWORD idInst, HSZ hszService, HSZ hszTopic, HCONVLIST hConvList, PCONVCONTEXT pCC)
{
  void *v5; // rbx
  HCONVLIST v6; // r14
  struct tagCL_INSTANCE_INFO *v9; // rdi
  HWND v10; // rax
  struct tagCL_CONV_INFO *v11; // rbx
  _QWORD *v12; // rax
  _QWORD *v13; // rsi
  HCONVLIST Handle; // rax
  HCONVLIST v15; // r13
  int *v16; // rcx
  _DWORD *v17; // rsi
  int v18; // edi
  LONG_PTR WindowLongPtrW; // r15
  struct tagCL_CONV_INFO *i; // rdi
  bool v21; // zf
  HWND v22; // rcx
  HWND v23; // rax
  struct tagCL_CONV_INFO *j; // rax
  struct tagCL_INSTANCE_INFO *v26; // [rsp+40h] [rbp-10h] BYREF
  HWND v27; // [rsp+48h] [rbp-8h] BYREF
  unsigned __int16 v28; // [rsp+90h] [rbp+40h] BYREF
  HSZ v29; // [rsp+98h] [rbp+48h] BYREF

  v29 = hszService;
  v5 = (void *)(int)idInst;
  v26 = 0;
  v6 = 0;
  v27 = 0;
  v28 = 0;
  RtlEnterCriticalSection(&gcsDDEML);
  if ( ValidateConnectParameters(v5, &v26, &v29, hszTopic, &v28, &pCC, &v27, hConvList) )
  {
    v9 = v26;
    if ( (*((_DWORD *)v26 + 14) & 0x3000) != 0 )
      v10 = (HWND)*((_QWORD *)v26 + 4);
    else
      v10 = 0;
    v11 = ConnectConv(v26, (unsigned __int16)v29, (unsigned __int16)hszTopic, v27, v10, pCC, hConvList, 2u);
    if ( !v11 )
    {
      SetLastDDEMLError(v9, 0x400Au);
      v6 = hConvList;
      goto LABEL_42;
    }
    if ( hConvList )
    {
      v16 = (int *)*((_QWORD *)aHandleEntry + 2 * (((unsigned __int64)hConvList >> 10) & 0x3FFF) + 1);
      v17 = LocalReAlloc(v16, 8LL * *v16 + 16, 0x42u);
      if ( !v17 )
      {
        SetLastDDEMLError(v9, 0x4008u);
        v6 = hConvList;
        goto LABEL_10;
      }
      v6 = hConvList;
      v15 = hConvList;
      *((_QWORD *)aHandleEntry + 2 * (((unsigned __int64)hConvList >> 10) & 0x3FFF) + 1) = v17;
      v18 = 0;
      for ( LODWORD(v26) = 0; v18 < *v17; LODWORD(v26) = v18 )
      {
        WindowLongPtrW = GetWindowLongPtrW(*(HWND *)&v17[2 * v18 + 2], 0);
        if ( v11 )
        {
          do
          {
            if ( !WindowLongPtrW )
              break;
            if ( (*(_BYTE *)(WindowLongPtrW + 56) & 1) != 0 )
            {
              for ( i = v11; i; i = (struct tagCL_CONV_INFO *)v22 )
              {
                v21 = (*((_BYTE *)i + 56) & 1) == 0;
                v22 = *(HWND *)i;
                v27 = *(HWND *)i;
                if ( !v21
                  && *(_QWORD *)(WindowLongPtrW + 112) == *((_QWORD *)i + 14)
                  && *(_WORD *)(WindowLongPtrW + 34) == *((_WORD *)i + 17)
                  && *(_WORD *)(WindowLongPtrW + 32) == *((_WORD *)i + 16) )
                {
                  ShutdownConversation(i, 0);
                  v23 = v27;
                  if ( i != v11 )
                    v23 = (HWND)v11;
                  v11 = (struct tagCL_CONV_INFO *)v23;
                  break;
                }
              }
            }
            WindowLongPtrW = *(_QWORD *)WindowLongPtrW;
          }
          while ( v11 );
          v18 = (int)v26;
        }
        ++v18;
      }
      for ( j = v11; j; j = *(struct tagCL_CONV_INFO **)j )
      {
        if ( (*((_BYTE *)j + 56) & 1) != 0 )
        {
          if ( !v11 )
            break;
          *(_QWORD *)&v17[2 * (*v17)++ + 2] = *((_QWORD *)v11 + 6);
          goto LABEL_39;
        }
      }
    }
    else
    {
      v12 = LocalAlloc(0x40u, 0x10u);
      v13 = v12;
      if ( !v12 )
      {
LABEL_9:
        SetLastDDEMLError(v9, 0x4008u);
LABEL_10:
        DisconnectConv(v11);
        goto LABEL_42;
      }
      Handle = (HCONVLIST)CreateHandle((unsigned __int64)v12, 4u, *((_DWORD *)v9 + 4) & 0x7F);
      v15 = Handle;
      if ( !Handle )
      {
        LocalFree(v13);
        goto LABEL_9;
      }
      v6 = Handle;
      v13[1] = *((_QWORD *)v11 + 6);
      *(_DWORD *)v13 = 1;
      do
      {
LABEL_39:
        if ( (*((_BYTE *)v11 + 56) & 1) != 0 )
          *((_QWORD *)v11 + 15) = v15;
        v11 = *(struct tagCL_CONV_INFO **)v11;
      }
      while ( v11 );
    }
  }
LABEL_42:
  if ( v28 )
    DeleteAtom(v28);
  RtlLeaveCriticalSection(&gcsDDEML);
  return v6;
}

```

## disassembly

```asm
0x180077370  mov     [rsp-38h+arg_10], rbx
0x180077375  mov     [rsp-38h+arg_8], rdx
0x18007737a  push    rbp
0x18007737b  push    rsi
0x18007737c  push    rdi
0x18007737d  push    r12
0x18007737f  push    r13
0x180077381  push    r14
0x180077383  push    r15
0x180077385  mov     rbp, rsp
0x180077388  sub     rsp, 50h
0x18007738c  xor     r15d, r15d
0x18007738f  movsxd  rbx, ecx
0x180077392  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180077399  mov     [rbp+var_10], r15
0x18007739d  mov     r14d, r15d
0x1800773a0  mov     [rbp+var_8], r15
0x1800773a4  mov     [rbp+arg_0], r15w
0x1800773a9  mov     r12, r9
0x1800773ac  mov     rsi, r8
0x1800773af  call    cs:__imp_RtlEnterCriticalSection
0x1800773b5  mov     [rsp+50h+var_18], r12; HCONVLIST
0x1800773ba  lea     rax, [rbp+var_8]
0x1800773be  mov     [rsp+50h+var_20], rax; HWND *
0x1800773c3  lea     r8, [rbp+arg_8]; HSZ *
0x1800773c7  lea     rax, [rbp+pCC]
0x1800773cb  mov     rcx, rbx; void *
0x1800773ce  mov     [rsp+50h+var_28], rax; struct tagCONVCONTEXT **
0x1800773d3  lea     rdx, [rbp+var_10]; struct tagCL_INSTANCE_INFO **
0x1800773d7  lea     rax, [rbp+arg_0]
0x1800773db  mov     r9, rsi; HSZ
0x1800773de  mov     [rsp+50h+var_30], rax; unsigned __int16 *
0x1800773e3  call    ?ValidateConnectParameters@@YAHPEAXPEAPEAUtagCL_INSTANCE_INFO@@PEAPEAUHSZ__@@PEAU2@PEAGPEAPEAUtagCONVCONTEXT@@PEAPEAUHWND__@@PEAUHCONVLIST__@@@Z; ValidateConnectParameters(void *,tagCL_INSTANCE_INFO * *,HSZ__ * *,HSZ__ *,ushort *,tagCONVCONTEXT * *,HWND__ * *,HCONVLIST__ *)
0x1800773e8  test    eax, eax
0x1800773ea  jz      loc_180077603
0x1800773f0  mov     rdi, [rbp+var_10]
0x1800773f4  mov     rcx, [rbp+pCC]
0x1800773f8  test    dword ptr [rdi+38h], 3000h
0x1800773ff  jz      short loc_180077407
0x180077401  mov     rax, [rdi+20h]
0x180077405  jmp     short loc_18007740A
0x180077407  mov     rax, r15
0x18007740a  mov     r9, [rbp+var_8]; HWND
0x18007740e  movzx   r8d, si; unsigned __int16
0x180077412  movzx   edx, word ptr [rbp+arg_8]; unsigned __int16
0x180077416  mov     dword ptr [rsp+50h+var_18], 2; unsigned int
0x18007741e  mov     [rsp+50h+var_20], r12; HCONVLIST
0x180077423  mov     [rsp+50h+var_28], rcx; struct tagCONVCONTEXT *
0x180077428  mov     rcx, rdi; struct tagCL_INSTANCE_INFO *
0x18007742b  mov     [rsp+50h+var_30], rax; HWND
0x180077430  call    ?ConnectConv@@YAPEAUtagCL_CONV_INFO@@PEAUtagCL_INSTANCE_INFO@@GGPEAUHWND__@@1PEAUtagCONVCONTEXT@@PEAUHCONVLIST__@@K@Z; ConnectConv(tagCL_INSTANCE_INFO *,ushort,ushort,HWND__ *,HWND__ *,tagCONVCONTEXT *,HCONVLIST__ *,ulong)
0x180077435  mov     rbx, rax
0x180077438  test    rax, rax
0x18007743b  jnz     short loc_180077452
0x18007743d  mov     edx, 400Ah; unsigned int
0x180077442  mov     rcx, rdi; struct tagCL_INSTANCE_INFO *
0x180077445  call    ?SetLastDDEMLError@@YAXPEAUtagCL_INSTANCE_INFO@@K@Z; SetLastDDEMLError(tagCL_INSTANCE_INFO *,ulong)
0x18007744a  mov     r14, r12
0x18007744d  jmp     loc_180077603
0x180077452  test    r12, r12
0x180077455  jnz     short loc_1800774C5
0x180077457  lea     edx, [r12+10h]; uBytes
0x18007745c  lea     ecx, [rdx+30h]; uFlags
0x18007745f  call    cs:__imp_LocalAlloc
0x180077465  mov     rsi, rax
0x180077468  test    rax, rax
0x18007746b  jnz     short loc_180077487
0x18007746d  mov     edx, 4008h; unsigned int
0x180077472  mov     rcx, rdi; struct tagCL_INSTANCE_INFO *
0x180077475  call    ?SetLastDDEMLError@@YAXPEAUtagCL_INSTANCE_INFO@@K@Z; SetLastDDEMLError(tagCL_INSTANCE_INFO *,ulong)
0x18007747a  mov     rcx, rbx; struct tagCONV_INFO *
0x18007747d  call    ?DisconnectConv@@YAXPEAUtagCONV_INFO@@@Z; DisconnectConv(tagCONV_INFO *)
0x180077482  jmp     loc_180077603
0x180077487  mov     r8d, [rdi+10h]
0x18007748b  mov     edx, 4; unsigned int
0x180077490  and     r8d, 7Fh; unsigned int
0x180077494  mov     rcx, rsi; unsigned __int64
0x180077497  call    ?CreateHandle@@YAPEAX_KKK@Z; CreateHandle(unsigned __int64,ulong,ulong)
0x18007749c  mov     r13, rax
0x18007749f  test    rax, rax
0x1800774a2  jnz     short loc_1800774AF
0x1800774a4  mov     rcx, rsi; hMem
0x1800774a7  call    cs:__imp_LocalFree
0x1800774ad  jmp     short loc_18007746D
0x1800774af  mov     r14, rax
0x1800774b2  mov     rax, [rbx+30h]
0x1800774b6  mov     [rsi+8], rax
0x1800774ba  mov     dword ptr [rsi], 1
0x1800774c0  jmp     loc_1800775F1
0x1800774c5  mov     rax, cs:?aHandleEntry@@3PEAUtagCHANDLEENTRY@@EA; tagCHANDLEENTRY * aHandleEntry
0x1800774cc  mov     r15, r12
0x1800774cf  shr     r15, 0Ah
0x1800774d3  mov     r8d, 42h ; 'B'; uFlags
0x1800774d9  and     r15d, 3FFFh
0x1800774e0  add     r15, r15
0x1800774e3  mov     rcx, [rax+r15*8+8]; hMem
0x1800774e8  movsxd  rdx, dword ptr [rcx]
0x1800774eb  lea     rdx, ds:10h[rdx*8]; uBytes
0x1800774f3  call    cs:__imp_LocalReAlloc
0x1800774f9  mov     rsi, rax
0x1800774fc  test    rax, rax
0x1800774ff  jnz     short loc_180077516
0x180077501  mov     edx, 4008h; unsigned int
0x180077506  mov     rcx, rdi; struct tagCL_INSTANCE_INFO *
0x180077509  call    ?SetLastDDEMLError@@YAXPEAUtagCL_INSTANCE_INFO@@K@Z; SetLastDDEMLError(tagCL_INSTANCE_INFO *,ulong)
0x18007750e  mov     r14, r12
0x180077511  jmp     loc_18007747A
0x180077516  mov     rax, cs:?aHandleEntry@@3PEAUtagCHANDLEENTRY@@EA; tagCHANDLEENTRY * aHandleEntry
0x18007751d  mov     r14, r12
0x180077520  mov     r13, r12
0x180077523  mov     [rax+r15*8+8], rsi
0x180077528  xor     r15d, r15d
0x18007752b  mov     edi, r15d
0x18007752e  mov     dword ptr [rbp+var_10], r15d
0x180077532  cmp     [rsi], r15d
0x180077535  jle     loc_1800775CB
0x18007753b  movsxd  rcx, edi
0x18007753e  xor     edx, edx; nIndex
0x180077540  mov     rcx, [rsi+rcx*8+8]; hWnd
0x180077545  call    GetWindowLongPtrW
0x18007754a  mov     r15, rax
0x18007754d  test    rbx, rbx
0x180077550  jz      short loc_1800775BB
0x180077552  test    r15, r15
0x180077555  jz      short loc_1800775B8
0x180077557  test    byte ptr [r15+38h], 1
0x18007755c  jz      short loc_1800775B0
0x18007755e  mov     rdi, rbx
0x180077561  test    rdi, rdi
0x180077564  jz      short loc_1800775B0
0x180077566  test    byte ptr [rdi+38h], 1
0x18007756a  mov     rcx, [rdi]
0x18007756d  mov     [rbp+var_8], rcx
0x180077571  jz      short loc_180077593
0x180077573  mov     rax, [rdi+70h]
0x180077577  cmp     [r15+70h], rax
0x18007757b  jnz     short loc_180077593
0x18007757d  movzx   eax, word ptr [rdi+22h]
0x180077581  cmp     [r15+22h], ax
0x180077586  jnz     short loc_180077593
0x180077588  movzx   eax, word ptr [rdi+20h]
0x18007758c  cmp     [r15+20h], ax
0x180077591  jz      short loc_180077598
0x180077593  mov     rdi, rcx
0x180077596  jmp     short loc_180077561
0x180077598  xor     edx, edx; int
0x18007759a  mov     rcx, rdi; struct tagCONV_INFO *
0x18007759d  call    ?ShutdownConversation@@YAXPEAUtagCONV_INFO@@H@Z; ShutdownConversation(tagCONV_INFO *,int)
0x1800775a2  mov     rax, [rbp+var_8]
0x1800775a6  cmp     rdi, rbx
0x1800775a9  cmovnz  rax, rbx
0x1800775ad  mov     rbx, rax
0x1800775b0  mov     r15, [r15]
0x1800775b3  test    rbx, rbx
0x1800775b6  jnz     short loc_180077552
0x1800775b8  mov     edi, dword ptr [rbp+var_10]
0x1800775bb  inc     edi
0x1800775bd  mov     dword ptr [rbp+var_10], edi
0x1800775c0  cmp     edi, [rsi]
0x1800775c2  jl      loc_18007753B
0x1800775c8  xor     r15d, r15d
0x1800775cb  mov     rax, rbx
0x1800775ce  test    rax, rax
0x1800775d1  jz      short loc_180077603
0x1800775d3  test    byte ptr [rax+38h], 1
0x1800775d7  jnz     short loc_1800775DE
0x1800775d9  mov     rax, [rax]
0x1800775dc  jmp     short loc_1800775CE
0x1800775de  test    rbx, rbx
0x1800775e1  jz      short loc_180077603
0x1800775e3  movsxd  rcx, dword ptr [rsi]
0x1800775e6  mov     rax, [rbx+30h]
0x1800775ea  mov     [rsi+rcx*8+8], rax
0x1800775ef  inc     dword ptr [rsi]
0x1800775f1  test    byte ptr [rbx+38h], 1
0x1800775f5  jz      short loc_1800775FB
0x1800775f7  mov     [rbx+78h], r13
0x1800775fb  mov     rbx, [rbx]
0x1800775fe  test    rbx, rbx
0x180077601  jnz     short loc_1800775F1
0x180077603  movzx   ecx, [rbp+arg_0]; nAtom
0x180077607  test    cx, cx
0x18007760a  jz      short loc_180077612
0x18007760c  call    cs:__imp_DeleteAtom
0x180077612  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180077619  call    cs:__imp_RtlLeaveCriticalSection
0x18007761f  mov     rbx, [rsp+50h+arg_10]
0x180077627  mov     rax, r14
0x18007762a  add     rsp, 50h
0x18007762e  pop     r15
0x180077630  pop     r14
0x180077632  pop     r13
0x180077634  pop     r12
0x180077636  pop     rdi
0x180077637  pop     rsi
0x180077638  pop     rbp
0x180077639  retn
```
