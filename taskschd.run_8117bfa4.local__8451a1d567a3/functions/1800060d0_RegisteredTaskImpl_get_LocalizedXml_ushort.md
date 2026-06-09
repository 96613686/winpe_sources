# RegisteredTaskImpl::get_LocalizedXml(ushort * *)

- ea: `0x1800060d0`
- end: `0x180006610`
- name: `?get_LocalizedXml@RegisteredTaskImpl@@AEAAJPEAPEAG@Z`
- size: `1344`
- prototype: `__int64 __fastcall(RegisteredTaskImpl *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180005ce0`

## callees

- `0x180001880`
- `0x1800060d0`
- `0x180007e90`
- `0x180010070`
- `0x18001f240`
- `0x180020ad0`
- `0x1800336f8`
- `0x180035130`
- `0x1800391c0`
- `0x18003c664`
- `0x18003e88c`
- `0x18004c7d8`
- `0x18005260b`
- `0x180058010`

## import_xrefs

- `msvcrt!malloc` at `0x180006120`
- `msvcrt!malloc` at `0x180006120`
- `msvcrt!free` at `0x1800061dc`
- `msvcrt!free` at `0x1800062d1`
- `msvcrt!free` at `0x18000632b`
- `msvcrt!free` at `0x1800061dc`
- `msvcrt!free` at `0x1800062d1`
- `msvcrt!free` at `0x18000632b`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x180006165`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x180006457`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x180006165`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x180006457`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006308`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006308`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006202`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006351`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006429`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006506`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006202`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006351`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006429`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006506`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800061ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000633d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006415`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800064f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800061ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000633d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006415`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800064f2`
- `OLEAUT32!__imp_SysAllocString` at `0x1800062b1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800062b1`
- `OLEAUT32!__imp_SysFreeString` at `0x180006240`
- `OLEAUT32!__imp_SysFreeString` at `0x180006299`
- `OLEAUT32!__imp_SysFreeString` at `0x1800064c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800065cb`
- `OLEAUT32!__imp_SysFreeString` at `0x180006240`
- `OLEAUT32!__imp_SysFreeString` at `0x180006299`
- `OLEAUT32!__imp_SysFreeString` at `0x1800064c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800065cb`
- `OLEAUT32!__imp_SysStringLen` at `0x18000651c`
- `OLEAUT32!__imp_SysStringLen` at `0x1800065a9`
- `OLEAUT32!__imp_SysStringLen` at `0x18000651c`
- `OLEAUT32!__imp_SysStringLen` at `0x1800065a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall RegisteredTaskImpl::get_LocalizedXml(RegisteredTaskImpl *this, unsigned __int16 **a2)
{
  int v4; // esi
  BSTR *v5; // r14
  WCHAR *v6; // rax
  WCHAR *v7; // rdi
  unsigned __int64 v8; // rax
  ULONG v9; // r8d
  const unsigned __int16 *v10; // rdx
  void *v11; // rbx
  HANDLE v12; // rax
  unsigned __int16 *v14; // rax
  RpcSession *v15; // rcx
  const OLECHAR *v16; // rbx
  BSTR v17; // rax
  void *v18; // rbx
  HANDLE v19; // rax
  signed int LastError; // eax
  unsigned int v21; // esi
  HANDLE v22; // rax
  void *v23; // rax
  HANDLE ProcessHeap; // rax
  int XmlLegacy; // ebx
  HANDLE v26; // rax
  UINT v27; // eax
  _WORD *v28; // rax
  const unsigned __int16 *v29; // rbx
  UINT v30; // eax
  LPVOID lpMem; // [rsp+30h] [rbp-C8h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-C0h] BYREF
  struct ITask *v33; // [rsp+40h] [rbp-B8h] BYREF
  PZZWSTR pwszLanguagesBuffer; // [rsp+48h] [rbp-B0h] BYREF
  void **pExceptionObject; // [rsp+50h] [rbp-A8h] BYREF
  char v36; // [rsp+58h] [rbp-A0h]
  __int64 *v37; // [rsp+60h] [rbp-98h]
  __int64 v38; // [rsp+68h] [rbp-90h]
  __int64 v39; // [rsp+70h] [rbp-88h]
  int v40; // [rsp+78h] [rbp-80h]
  __int64 v41; // [rsp+7Ch] [rbp-7Ch]
  void **v42; // [rsp+88h] [rbp-70h] BYREF
  char v43; // [rsp+90h] [rbp-68h]
  __int64 *v44; // [rsp+98h] [rbp-60h]
  __int64 v45; // [rsp+A0h] [rbp-58h]
  __int64 v46; // [rsp+A8h] [rbp-50h]
  int v47; // [rsp+B0h] [rbp-48h]
  __int64 v48; // [rsp+B4h] [rbp-44h]
  ULONG pcchLanguagesBuffer; // [rsp+110h] [rbp+18h] BYREF
  ULONG pulNumLanguages; // [rsp+118h] [rbp+20h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v4 = 0;
  v5 = (BSTR *)((char *)this + 120);
  if ( *((_QWORD *)this + 15) )
    goto LABEL_16;
  lpMem = 0;
  pulNumLanguages = 0;
  pcchLanguagesBuffer = 200;
  v6 = (WCHAR *)malloc(0x190u);
  v7 = v6;
  if ( !v6 )
  {
    v36 = 0;
    v37 = &qword_18007B2F0;
    v38 = 0;
    v39 = 0;
    v40 = 14;
    v41 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  pwszLanguagesBuffer = v6;
  memset_0(v6, 0, 0x190u);
  if ( GetThreadPreferredUILanguages(0x28u, &pulNumLanguages, v7, &pcchLanguagesBuffer) )
    goto LABEL_5;
  if ( GetLastError() == 111 )
  {
    wmi::AutoVectorPtr<unsigned short>::Delete(&pwszLanguagesBuffer);
    v23 = operator new(saturated_mul(pcchLanguagesBuffer, 2u));
    wmi::AutoVectorPtr<unsigned short>::operator=(&pwszLanguagesBuffer, v23);
    v7 = pwszLanguagesBuffer;
    if ( !pwszLanguagesBuffer )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
      return 2147942414LL;
    }
    if ( GetThreadPreferredUILanguages(0x28u, &pulNumLanguages, pwszLanguagesBuffer, &pcchLanguagesBuffer) )
    {
LABEL_5:
      v8 = 0;
      v9 = pcchLanguagesBuffer;
      if ( pcchLanguagesBuffer != 1 )
      {
        do
        {
          if ( !v7[v8] )
          {
            v7[v8] = 92;
            v9 = pcchLanguagesBuffer;
          }
          ++v8;
        }
        while ( v8 < v9 - 1 );
      }
      v10 = (const unsigned __int16 *)((char *)this + 80);
      if ( *((_QWORD *)this + 13) >= 8u )
        v10 = *(const unsigned __int16 **)v10;
      if ( !*((_DWORD *)this + 32) )
      {
        v4 = -2147023645;
LABEL_13:
        if ( v7 )
          free(v7);
        v11 = lpMem;
        v12 = GetProcessHeap();
        HeapFree(v12, 0, v11);
        return (unsigned int)v4;
      }
      v15 = (RpcSession *)*((_QWORD *)this + 17);
      if ( v15 )
      {
        v4 = RpcSession::RetrieveTask(v15, v10, v7, &pulNumLanguages, (struct RpcString *)&lpMem);
        if ( v4 < 0 )
          goto LABEL_13;
        goto LABEL_21;
      }
      if ( v10 && *v10 == 92 )
        ++v10;
      v33 = 0;
      XmlLegacy = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, GUID *, struct ITask **))(**((_QWORD **)this + 18) + 48LL))(
                    *((_QWORD *)this + 18),
                    v10,
                    &GUID_148bd524_a2ab_11ce_b11f_00aa00530503,
                    &v33);
      if ( XmlLegacy >= 0 )
      {
        bstrString = 0;
        XmlLegacy = UniSession::GenerateXmlLegacy(v33, (struct ATL::CComBSTR *)&bstrString);
        if ( XmlLegacy >= 0 )
        {
          v26 = GetProcessHeap();
          HeapFree(v26, 0, lpMem);
          v27 = SysStringLen(bstrString);
          v28 = MIDL_user_allocate(2LL * (v27 + 1));
          lpMem = v28;
          if ( !v28 )
          {
            v43 = 0;
            v44 = &qword_18007B2F0;
            v45 = 0;
            v46 = 0;
            v47 = 14;
            v48 = -1;
            v42 = &wmi::GenericException::`vftable';
            throw (wmi::OutOfMemoryException *)&v42;
          }
          *v28 = 0;
          v29 = bstrString;
          v30 = SysStringLen(bstrString);
          StringCchCopyW((unsigned __int16 *)lpMem, v30 + 1, v29);
          SysFreeString(bstrString);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
LABEL_21:
          v16 = (const OLECHAR *)lpMem;
          if ( lpMem != *v5 )
          {
            SysFreeString(*v5);
            if ( v16 )
            {
              v17 = SysAllocString(v16);
              *v5 = v17;
              if ( !v17 )
                ATL::PrivateAtlThrow(-2147024882);
            }
            else
            {
              *v5 = 0;
            }
          }
          if ( v7 )
            free(v7);
          v18 = lpMem;
          v19 = GetProcessHeap();
          HeapFree(v19, 0, v18);
LABEL_16:
          v14 = ATL::CComBSTR::Copy((ATL::CComBSTR *)v5);
          if ( *v5 && !v14 )
            ATL::PrivateAtlThrow(-2147024882);
          *a2 = v14;
          SysFreeString(0);
          return (unsigned int)v4;
        }
        SysFreeString(bstrString);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
      v4 = XmlLegacy;
      goto LABEL_13;
    }
  }
  LastError = GetLastError();
  v21 = LastError;
  if ( LastError > 0 )
    v21 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 )
    free(v7);
  v22 = GetProcessHeap();
  HeapFree(v22, 0, lpMem);
  return v21;
}

```

## disassembly

```asm
0x1800060d0  mov     rax, rsp
0x1800060d3  push    rbx
0x1800060d4  push    rsi
0x1800060d5  push    rdi
0x1800060d6  push    r12
0x1800060d8  push    r13
0x1800060da  push    r14
0x1800060dc  push    r15
0x1800060de  sub     rsp, 0C0h
0x1800060e5  mov     r15, rdx
0x1800060e8  mov     rbx, rcx
0x1800060eb  test    rdx, rdx
0x1800060ee  jz      loc_180006364
0x1800060f4  xor     r13d, r13d
0x1800060f7  mov     esi, r13d
0x1800060fa  mov     [rax+10h], r13d
0x1800060fe  lea     r14, [rcx+78h]
0x180006102  cmp     [r14], r13
0x180006105  jnz     loc_180006224
0x18000610b  mov     [rsp+0F8h+lpMem], r13
0x180006110  mov     [rax+20h], r13d
0x180006114  mov     dword ptr [rax+18h], 0C8h
0x18000611b  mov     ecx, 190h; Size
0x180006120  call    cs:__imp_malloc
0x180006127  nop     dword ptr [rax+rax+00h]
0x18000612c  mov     rdi, rax
0x18000612f  test    rax, rax
0x180006132  jz      loc_18000636E
0x180006138  mov     [rsp+0F8h+pwszLanguagesBuffer], rax
0x18000613d  xor     edx, edx; Val
0x18000613f  mov     r8d, 190h; Size
0x180006145  mov     rcx, rax; void *
0x180006148  call    memset_0
0x18000614d  lea     r9, [rsp+0F8h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x180006155  mov     r8, rdi; pwszLanguagesBuffer
0x180006158  lea     rdx, [rsp+0F8h+pulNumLanguages]; pulNumLanguages
0x180006160  mov     ecx, 28h ; '('; dwFlags
0x180006165  call    cs:__imp_GetThreadPreferredUILanguages
0x18000616c  nop     dword ptr [rax+rax+00h]
0x180006171  test    eax, eax
0x180006173  jz      loc_1800063B8
0x180006179  mov     rax, r13
0x18000617c  mov     r8d, [rsp+0F8h+pcchLanguagesBuffer]
0x180006184  lea     ecx, [r8-1]
0x180006188  test    ecx, ecx
0x18000618a  jz      short loc_1800061AD
0x18000618c  cmp     word ptr [rdi+rax*2], 0
0x180006191  jnz     short loc_1800061A1
0x180006193  mov     word ptr [rdi+rax*2], 5Ch ; '\'
0x180006199  mov     r8d, [rsp+0F8h+pcchLanguagesBuffer]
0x1800061a1  inc     rax
0x1800061a4  lea     edx, [r8-1]
0x1800061a8  cmp     rax, rdx
0x1800061ab  jb      short loc_18000618C
0x1800061ad  lea     rdx, [rbx+50h]
0x1800061b1  cmp     qword ptr [rdx+18h], 8
0x1800061b6  jb      short loc_1800061BB
0x1800061b8  mov     rdx, [rdx]; unsigned __int16 *
0x1800061bb  cmp     dword ptr [rbx+80h], 0
0x1800061c2  jnz     loc_180006251
0x1800061c8  mov     esi, 800704E3h
0x1800061cd  mov     [rsp+0F8h+arg_8], esi
0x1800061d4  test    rdi, rdi
0x1800061d7  jz      short loc_1800061E9
0x1800061d9  mov     rcx, rdi; Block
0x1800061dc  call    cs:__imp_free
0x1800061e3  nop     dword ptr [rax+rax+00h]
0x1800061e8  nop
0x1800061e9  mov     rbx, [rsp+0F8h+lpMem]
0x1800061ee  call    cs:__imp_GetProcessHeap
0x1800061f5  nop     dword ptr [rax+rax+00h]
0x1800061fa  mov     r8, rbx; lpMem
0x1800061fd  xor     edx, edx; dwFlags
0x1800061ff  mov     rcx, rax; hHeap
0x180006202  call    cs:__imp_HeapFree
0x180006209  nop     dword ptr [rax+rax+00h]
0x18000620e  mov     eax, esi
0x180006210  add     rsp, 0C0h
0x180006217  pop     r15
0x180006219  pop     r14
0x18000621b  pop     r13
0x18000621d  pop     r12
0x18000621f  pop     rdi
0x180006220  pop     rsi
0x180006221  pop     rbx
0x180006222  retn
0x180006224  mov     rcx, r14; this
0x180006227  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x18000622c  cmp     qword ptr [r14], 0
0x180006230  jz      short loc_18000623B
0x180006232  test    rax, rax
0x180006235  jz      loc_1800065F9
0x18000623b  mov     [r15], rax
0x18000623e  xor     ecx, ecx; bstrString
0x180006240  call    cs:__imp_SysFreeString
0x180006247  nop     dword ptr [rax+rax+00h]
0x18000624c  nop
0x18000624d  mov     eax, esi
0x18000624f  jmp     short loc_180006210
0x180006251  mov     rcx, [rbx+88h]; this
0x180006258  test    rcx, rcx
0x18000625b  jz      loc_180006470
0x180006261  lea     rax, [rsp+0F8h+lpMem]
0x180006266  mov     [rsp+0F8h+var_D8], rax; struct RpcString *
0x18000626b  lea     r9, [rsp+0F8h+pulNumLanguages]; unsigned int *
0x180006273  mov     r8, rdi; unsigned __int16 *
0x180006276  call    ?RetrieveTask@RpcSession@@QEBAJPEBG0PEAKAEAVRpcString@@@Z; RpcSession::RetrieveTask(ushort const *,ushort const *,ulong *,RpcString &)
0x18000627b  mov     esi, eax
0x18000627d  mov     [rsp+0F8h+arg_8], eax
0x180006284  test    eax, eax
0x180006286  js      loc_1800061D4
0x18000628c  mov     rbx, [rsp+0F8h+lpMem]
0x180006291  mov     rcx, [r14]; bstrString
0x180006294  cmp     rbx, rcx
0x180006297  jz      short loc_1800062C9
0x180006299  call    cs:__imp_SysFreeString
0x1800062a0  nop     dword ptr [rax+rax+00h]
0x1800062a5  test    rbx, rbx
0x1800062a8  jz      loc_1800065F1
0x1800062ae  mov     rcx, rbx; psz
0x1800062b1  call    cs:__imp_SysAllocString
0x1800062b8  nop     dword ptr [rax+rax+00h]
0x1800062bd  mov     [r14], rax
0x1800062c0  test    rax, rax
0x1800062c3  jz      loc_1800065E7
0x1800062c9  test    rdi, rdi
0x1800062cc  jz      short loc_1800062DE
0x1800062ce  mov     rcx, rdi; Block
0x1800062d1  call    cs:__imp_free
0x1800062d8  nop     dword ptr [rax+rax+00h]
0x1800062dd  nop
0x1800062de  mov     rbx, [rsp+0F8h+lpMem]
0x1800062e3  call    cs:__imp_GetProcessHeap
0x1800062ea  nop     dword ptr [rax+rax+00h]
0x1800062ef  mov     r8, rbx; lpMem
0x1800062f2  xor     edx, edx; dwFlags
0x1800062f4  mov     rcx, rax; hHeap
0x1800062f7  call    cs:__imp_HeapFree
0x1800062fe  nop     dword ptr [rax+rax+00h]
0x180006303  jmp     loc_180006224
0x180006308  call    cs:__imp_GetLastError
0x18000630f  nop     dword ptr [rax+rax+00h]
0x180006314  mov     esi, eax
0x180006316  test    eax, eax
0x180006318  jle     short loc_180006323
0x18000631a  movzx   esi, ax
0x18000631d  or      esi, 80070000h
0x180006323  test    rdi, rdi
0x180006326  jz      short loc_180006338
0x180006328  mov     rcx, rdi; Block
0x18000632b  call    cs:__imp_free
0x180006332  nop     dword ptr [rax+rax+00h]
0x180006337  nop
0x180006338  mov     rbx, [rsp+0F8h+lpMem]
0x18000633d  call    cs:__imp_GetProcessHeap
0x180006344  nop     dword ptr [rax+rax+00h]
0x180006349  mov     r8, rbx; lpMem
0x18000634c  xor     edx, edx; dwFlags
0x18000634e  mov     rcx, rax; hHeap
0x180006351  call    cs:__imp_HeapFree
0x180006358  nop     dword ptr [rax+rax+00h]
0x18000635d  mov     eax, esi
0x18000635f  jmp     loc_180006210
0x180006364  mov     eax, 80004003h
0x180006369  jmp     loc_180006210
0x18000636e  mov     [rsp+0F8h+var_A0], 0
0x180006373  lea     rax, qword_18007B2F0
0x18000637a  mov     [rsp+0F8h+var_98], rax
0x18000637f  mov     [rsp+0F8h+var_90], r13
0x180006384  mov     [rsp+0F8h+var_88], r13
0x180006389  mov     [rsp+0F8h+var_80], 0Eh
0x180006391  mov     [rsp+0F8h+var_7C], 0FFFFFFFFFFFFFFFFh
0x18000639a  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800063a1  mov     [rsp+0F8h+pExceptionObject], rax
0x1800063a6  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x1800063ad  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x1800063b2  call    _CxxThrowException_0
0x1800063b8  call    cs:__imp_GetLastError
0x1800063bf  nop     dword ptr [rax+rax+00h]
0x1800063c4  cmp     eax, 6Fh ; 'o'
0x1800063c7  jnz     loc_180006308
0x1800063cd  lea     rcx, [rsp+0F8h+pwszLanguagesBuffer]
0x1800063d2  call    ?Delete@?$AutoVectorPtr@G@wmi@@QEAAXXZ; wmi::AutoVectorPtr<ushort>::Delete(void)
0x1800063d7  mov     ecx, [rsp+0F8h+pcchLanguagesBuffer]
0x1800063de  mov     eax, 2
0x1800063e3  mul     rcx
0x1800063e6  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800063ed  cmovb   rax, r12
0x1800063f1  mov     rcx, rax; unsigned __int64
0x1800063f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800063f9  mov     rdx, rax
0x1800063fc  lea     rcx, [rsp+0F8h+pwszLanguagesBuffer]
0x180006401  call    ??4?$AutoVectorPtr@G@wmi@@QEAAAEAV01@PEAG@Z; wmi::AutoVectorPtr<ushort>::operator=(ushort *)
0x180006406  mov     rdi, [rsp+0F8h+pwszLanguagesBuffer]
0x18000640b  test    rdi, rdi
0x18000640e  jnz     short loc_18000643F
0x180006410  mov     rbx, [rsp+0F8h+lpMem]
0x180006415  call    cs:__imp_GetProcessHeap
0x18000641c  nop     dword ptr [rax+rax+00h]
0x180006421  mov     r8, rbx; lpMem
0x180006424  xor     edx, edx; dwFlags
0x180006426  mov     rcx, rax; hHeap
0x180006429  call    cs:__imp_HeapFree
0x180006430  nop     dword ptr [rax+rax+00h]
0x180006435  mov     eax, 8007000Eh
0x18000643a  jmp     loc_180006210
0x18000643f  lea     r9, [rsp+0F8h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x180006447  mov     r8, rdi; pwszLanguagesBuffer
0x18000644a  lea     rdx, [rsp+0F8h+pulNumLanguages]; pulNumLanguages
0x180006452  mov     ecx, 28h ; '('; dwFlags
0x180006457  call    cs:__imp_GetThreadPreferredUILanguages
0x18000645e  nop     dword ptr [rax+rax+00h]
0x180006463  test    eax, eax
0x180006465  jnz     loc_180006179
0x18000646b  jmp     loc_180006308
0x180006470  test    rdx, rdx
0x180006473  jz      short loc_18000647F
0x180006475  cmp     word ptr [rdx], 5Ch ; '\'
0x180006479  jnz     short loc_18000647F
0x18000647b  add     rdx, 2
0x18000647f  mov     [rsp+0F8h+var_B8], r13
0x180006484  mov     rcx, [rbx+90h]
0x18000648b  mov     rax, [rcx]
0x18000648e  lea     r9, [rsp+0F8h+var_B8]
0x180006493  lea     r8, _GUID_148bd524_a2ab_11ce_b11f_00aa00530503
0x18000649a  mov     rax, [rax+30h]
0x18000649e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064a3  mov     ebx, eax
0x1800064a5  test    eax, eax
0x1800064a7  js      short loc_1800064D5
0x1800064a9  mov     [rsp+0F8h+bstrString], r13
0x1800064ae  lea     rdx, [rsp+0F8h+bstrString]; struct ATL::CComBSTR *
0x1800064b3  mov     rcx, [rsp+0F8h+var_B8]; struct ITask *
0x1800064b8  call    ?GenerateXmlLegacy@UniSession@@CAJPEAUITask@@AEAVCComBSTR@ATL@@@Z; UniSession::GenerateXmlLegacy(ITask *,ATL::CComBSTR &)
0x1800064bd  mov     ebx, eax
0x1800064bf  test    eax, eax
0x1800064c1  jns     short loc_1800064ED
0x1800064c3  mov     rcx, [rsp+0F8h+bstrString]; bstrString
0x1800064c8  call    cs:__imp_SysFreeString
0x1800064cf  nop     dword ptr [rax+rax+00h]
0x1800064d4  nop
0x1800064d5  lea     rcx, [rsp+0F8h+var_B8]
0x1800064da  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800064df  mov     [rsp+0F8h+arg_8], ebx
0x1800064e6  mov     esi, ebx
0x1800064e8  jmp     loc_1800061D4
0x1800064ed  mov     rbx, [rsp+0F8h+lpMem]
0x1800064f2  call    cs:__imp_GetProcessHeap
0x1800064f9  nop     dword ptr [rax+rax+00h]
0x1800064fe  mov     r8, rbx; lpMem
0x180006501  xor     edx, edx; dwFlags
0x180006503  mov     rcx, rax; hHeap
0x180006506  call    cs:__imp_HeapFree
0x18000650d  nop     dword ptr [rax+rax+00h]
0x180006512  mov     [rsp+0F8h+lpMem], r13
0x180006517  mov     rcx, [rsp+0F8h+bstrString]; pbstr
0x18000651c  call    cs:__imp_SysStringLen
0x180006523  nop     dword ptr [rax+rax+00h]
0x180006528  lea     ecx, [rax+1]
0x18000652b  add     rcx, rcx; size
0x18000652e  call    MIDL_user_allocate
0x180006533  mov     [rsp+0F8h+lpMem], rax
0x180006538  test    rax, rax
0x18000653b  jnz     short loc_18000659D
0x18000653d  mov     [rsp+0F8h+var_68], al
0x180006544  lea     rax, qword_18007B2F0
0x18000654b  mov     [rsp+0F8h+var_60], rax
0x180006553  mov     [rsp+0F8h+var_58], r13
0x18000655b  mov     [rsp+0F8h+var_50], r13
0x180006563  mov     [rsp+0F8h+var_48], 0Eh
0x18000656e  mov     [rsp+0F8h+var_44], 0FFFFFFFFFFFFFFFFh
0x18000657a  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180006581  mov     [rsp+0F8h+var_70], rax
0x180006589  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180006590  lea     rcx, [rsp+0F8h+var_70]; pExceptionObject
0x180006598  call    _CxxThrowException_0
0x18000659d  mov     [rax], r13w
0x1800065a1  mov     rbx, [rsp+0F8h+bstrString]
0x1800065a6  mov     rcx, rbx; pbstr
0x1800065a9  call    cs:__imp_SysStringLen
0x1800065b0  nop     dword ptr [rax+rax+00h]
0x1800065b5  lea     edx, [rax+1]; unsigned __int64
0x1800065b8  mov     r8, rbx; unsigned __int16 *
0x1800065bb  mov     rcx, [rsp+0F8h+lpMem]; unsigned __int16 *
0x1800065c0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800065c5  nop
0x1800065c6  mov     rcx, [rsp+0F8h+bstrString]; bstrString
0x1800065cb  call    cs:__imp_SysFreeString
0x1800065d2  nop     dword ptr [rax+rax+00h]
0x1800065d7  nop
0x1800065d8  lea     rcx, [rsp+0F8h+var_B8]
0x1800065dd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800065e2  jmp     loc_18000628C
0x1800065e7  mov     ecx, 8007000Eh; int
0x1800065ec  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x1800065f1  mov     [r14], r13
0x1800065f4  jmp     loc_1800062C9
0x1800065f9  mov     ecx, 8007000Eh; int
0x1800065fe  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180006604  mov     esi, [rsp+0F8h+arg_8]
  ... truncated ...
```
