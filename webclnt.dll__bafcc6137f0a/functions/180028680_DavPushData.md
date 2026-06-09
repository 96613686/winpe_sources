# DavPushData

- ea: `0x180028680`
- end: `0x1800288e1`
- name: `DavPushData`
- size: `609`
- prototype: `__int64 __fastcall(__int64, _QWORD *, LPVOID *, unsigned int, unsigned int)`
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800049bc`
- `0x18001507c`
- `0x18001a5a0`
- `0x18001ad0c`
- `0x18001dcb4`
- `0x1800206bc`
- `0x1800229b0`

## callees

- `0x180001008`
- `0x18000b7dc`
- `0x18000b89c`
- `0x180028680`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028754`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800287cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002880e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002885b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800288a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028754`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800287cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002880e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002885b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800288a0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800287a0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800287a0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180028727`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180028727`

## pseudocode

```c
__int64 __fastcall DavPushData(__int64 a1, _QWORD *a2, LPVOID *a3, unsigned int a4, unsigned int a5)
{
  bool v5; // zf
  LPVOID v7; // rcx
  _DWORD *v11; // rax
  _DWORD *v12; // rbx
  HRESULT v13; // edi
  DWORD v14; // eax
  __int64 v15; // rdx
  LPVOID v16; // rcx
  DWORD v17; // eax
  __int64 v18; // rdx
  DWORD CurrentThreadId; // eax
  LPVOID ppv; // [rsp+58h] [rbp+10h] BYREF

  v5 = *a2 == 0;
  v7 = *a3;
  ppv = *a3;
  if ( v5 )
  {
    v11 = operator new(0x48u);
    v12 = v11;
    if ( !v11 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        CurrentThreadId = GetCurrentThreadId();
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          40,
          WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids,
          CurrentThreadId);
      }
      return 1450;
    }
    v11[2] = 0;
    *(_QWORD *)v11 = &CDavNodeFactory::`vftable';
    *((_QWORD *)v11 + 2) = 0;
    *((_QWORD *)v11 + 3) = 0;
    *((_QWORD *)v11 + 4) = 0;
    v11[10] = 0;
    v11[11] = 17;
    *((_QWORD *)v11 + 6) = 0;
    *((_QWORD *)v11 + 7) = 0;
    v11[16] = -1;
    CDavNodeFactory::AddRef((CDavNodeFactory *)v11);
    *a2 = v12;
    v13 = CoInitializeEx(0, 0);
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        return 87;
      v14 = GetCurrentThreadId();
      v15 = 41;
      goto LABEL_7;
    }
    v13 = CoCreateInstance(&CLSID_XMLParser, 0, 1u, &IID_IXMLParser, &ppv);
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        return 87;
      v14 = GetCurrentThreadId();
      v15 = 42;
LABEL_7:
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids, v14, v13);
      return 87;
    }
    v16 = ppv;
    *a3 = ppv;
    if ( (*(int (__fastcall **)(LPVOID, _DWORD *))(*(_QWORD *)v16 + 24LL))(v16, v12) < 0 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        return 87;
      v17 = GetCurrentThreadId();
      v18 = 43;
      goto LABEL_21;
    }
    v7 = ppv;
  }
  if ( (*(int (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD))(*(_QWORD *)v7 + 136LL))(v7, a1, a4, a5) < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      return 87;
    v17 = GetCurrentThreadId();
    v18 = 44;
LABEL_21:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids, v17);
    return 87;
  }
  return 0;
}

```

## disassembly

```asm
0x180028680  mov     [rsp+arg_0], rbx
0x180028685  mov     [rsp+arg_10], rbp
0x18002868a  push    rsi
0x18002868b  push    rdi
0x18002868c  push    r14
0x18002868e  sub     rsp, 30h
0x180028692  cmp     qword ptr [rdx], 0
0x180028696  mov     r14, rcx
0x180028699  mov     rcx, [r8]
0x18002869c  mov     ebp, r9d
0x18002869f  mov     [rsp+48h+arg_8], rcx
0x1800286a4  mov     rsi, r8
0x1800286a7  mov     rdi, rdx
0x1800286aa  jnz     loc_180028820
0x1800286b0  mov     ecx, 48h ; 'H'; Size
0x1800286b5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800286ba  mov     rbx, rax
0x1800286bd  test    rax, rax
0x1800286c0  jz      loc_180028887
0x1800286c6  lea     rax, ??_7CDavNodeFactory@@6B@; const CDavNodeFactory::`vftable'
0x1800286cd  mov     dword ptr [rbx+8], 0
0x1800286d4  mov     [rbx], rax
0x1800286d7  mov     rcx, rbx
0x1800286da  mov     rax, [rax+8]
0x1800286de  mov     qword ptr [rbx+10h], 0
0x1800286e6  mov     qword ptr [rbx+18h], 0
0x1800286ee  mov     qword ptr [rbx+20h], 0
0x1800286f6  mov     dword ptr [rbx+28h], 0
0x1800286fd  mov     dword ptr [rbx+2Ch], 11h
0x180028704  mov     qword ptr [rbx+30h], 0
0x18002870c  mov     qword ptr [rbx+38h], 0
0x180028714  mov     dword ptr [rbx+40h], 0FFFFFFFFh
0x18002871b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028720  xor     edx, edx; dwCoInit
0x180028722  mov     [rdi], rbx
0x180028725  xor     ecx, ecx; pvReserved
0x180028727  call    cs:__imp_CoInitializeEx
0x18002872d  mov     edi, eax
0x18002872f  test    eax, eax
0x180028731  jns     short loc_180028782
0x180028733  mov     rdx, cs:WPP_GLOBAL_Control
0x18002873a  lea     rcx, WPP_GLOBAL_Control
0x180028741  cmp     rdx, rcx
0x180028744  jz      loc_180028880
0x18002874a  test    byte ptr [rdx+1Ch], 8
0x18002874e  jz      loc_180028880
0x180028754  call    cs:__imp_GetCurrentThreadId
0x18002875a  mov     edx, 29h ; ')'
0x18002875f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028766  lea     r8, WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids
0x18002876d  mov     r9d, eax
0x180028770  mov     dword ptr [rsp+48h+ppv], edi
0x180028774  mov     rcx, [rcx+10h]
0x180028778  call    WPP_SF_Dd
0x18002877d  jmp     loc_180028880
0x180028782  xor     edx, edx; pUnkOuter
0x180028784  lea     rax, [rsp+48h+arg_8]
0x180028789  lea     r9, IID_IXMLParser; riid
0x180028790  mov     [rsp+48h+ppv], rax; ppv
0x180028795  lea     rcx, CLSID_XMLParser; rclsid
0x18002879c  lea     r8d, [rdx+1]; dwClsContext
0x1800287a0  call    cs:__imp_CoCreateInstance
0x1800287a6  mov     edi, eax
0x1800287a8  test    eax, eax
0x1800287aa  jns     short loc_1800287DA
0x1800287ac  mov     rdx, cs:WPP_GLOBAL_Control
0x1800287b3  lea     rcx, WPP_GLOBAL_Control
0x1800287ba  cmp     rdx, rcx
0x1800287bd  jz      loc_180028880
0x1800287c3  test    byte ptr [rdx+1Ch], 8
0x1800287c7  jz      loc_180028880
0x1800287cd  call    cs:__imp_GetCurrentThreadId
0x1800287d3  mov     edx, 2Ah ; '*'
0x1800287d8  jmp     short loc_18002875F
0x1800287da  mov     rcx, [rsp+48h+arg_8]
0x1800287df  mov     rdx, rbx
0x1800287e2  mov     [rsi], rcx
0x1800287e5  mov     rax, [rcx]
0x1800287e8  mov     rax, [rax+18h]
0x1800287ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800287f1  test    eax, eax
0x1800287f3  jns     short loc_18002881B
0x1800287f5  mov     rax, cs:WPP_GLOBAL_Control
0x1800287fc  lea     rcx, WPP_GLOBAL_Control
0x180028803  cmp     rax, rcx
0x180028806  jz      short loc_180028880
0x180028808  test    byte ptr [rax+1Ch], 8
0x18002880c  jz      short loc_180028880
0x18002880e  call    cs:__imp_GetCurrentThreadId
0x180028814  mov     edx, 2Bh ; '+'
0x180028819  jmp     short loc_180028866
0x18002881b  mov     rcx, [rsp+48h+arg_8]
0x180028820  mov     rax, [rcx]
0x180028823  mov     r8d, ebp
0x180028826  mov     r9d, [rsp+48h+arg_20]
0x18002882b  mov     rdx, r14
0x18002882e  mov     rax, [rax+88h]
0x180028835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002883a  test    eax, eax
0x18002883c  jns     loc_1800288CC
0x180028842  mov     rax, cs:WPP_GLOBAL_Control
0x180028849  lea     rcx, WPP_GLOBAL_Control
0x180028850  cmp     rax, rcx
0x180028853  jz      short loc_180028880
0x180028855  test    byte ptr [rax+1Ch], 8
0x180028859  jz      short loc_180028880
0x18002885b  call    cs:__imp_GetCurrentThreadId
0x180028861  mov     edx, 2Ch ; ','
0x180028866  mov     rcx, cs:WPP_GLOBAL_Control
0x18002886d  lea     r8, WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids
0x180028874  mov     r9d, eax
0x180028877  mov     rcx, [rcx+10h]
0x18002887b  call    WPP_SF_d
0x180028880  mov     eax, 57h ; 'W'
0x180028885  jmp     short loc_1800288CE
0x180028887  mov     rax, cs:WPP_GLOBAL_Control
0x18002888e  lea     rcx, WPP_GLOBAL_Control
0x180028895  cmp     rax, rcx
0x180028898  jz      short loc_1800288C5
0x18002889a  test    byte ptr [rax+1Ch], 8
0x18002889e  jz      short loc_1800288C5
0x1800288a0  call    cs:__imp_GetCurrentThreadId
0x1800288a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800288ad  lea     r8, WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids
0x1800288b4  mov     edx, 28h ; '('
0x1800288b9  mov     r9d, eax
0x1800288bc  mov     rcx, [rcx+10h]
0x1800288c0  call    WPP_SF_d
0x1800288c5  mov     eax, 5AAh
0x1800288ca  jmp     short loc_1800288CE
0x1800288cc  xor     eax, eax
0x1800288ce  mov     rbx, [rsp+48h+arg_0]
0x1800288d3  mov     rbp, [rsp+48h+arg_10]
0x1800288d8  add     rsp, 30h
0x1800288dc  pop     r14
0x1800288de  pop     rdi
0x1800288df  pop     rsi
0x1800288e0  retn
```
