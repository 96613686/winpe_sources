# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x180042638`
- end: `0x1800427cd`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004518c`

## callees

- `0x18001fa00`
- `0x180041d48`
- `0x180042638`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800426e2`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800426e2`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        HRESULT a2,
        __int64 a3)
{
  int v4; // ebx
  char v5; // bl
  int (__fastcall *v6)(_QWORD, GUID *, __int64 *); // rbx
  int (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rbx
  HANDLE pHandles[3]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v10; // [rsp+70h] [rbp+20h] BYREF
  HRESULT v11; // [rsp+78h] [rbp+28h] BYREF
  __int64 dwindex; // [rsp+80h] [rbp+30h] BYREF
  __int64 v13; // [rsp+88h] [rbp+38h] BYREF

  dwindex = a3;
  v11 = a2;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[1])(a1);
  v13 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  v4 = ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(&v13);
  v11 = v4;
  if ( v4 >= 0 )
  {
    v4 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*a1)[6])(a1, v13);
    v11 = v4;
    if ( v4 >= 0 )
    {
      pHandles[0] = *(HANDLE *)(v13 + 56);
      pHandles[1] = 0;
      v5 = 0;
      LODWORD(dwindex) = 0;
      v11 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, pHandles, (LPDWORD)&dwindex);
      if ( v11 >= 0 && (_DWORD)dwindex )
      {
        v11 = -2147023673;
        v5 = 1;
      }
      v10 = 0;
      if ( v5 )
      {
        v6 = **a1;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
        if ( v6(a1, &GUID_00000036_0000_0000_c000_000000000046, &v10) >= 0 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 72LL))(v10);
      }
      if ( v11 >= 0 && *(_DWORD *)(v13 + 48) != 1 )
      {
        if ( v10
          || (v7 = **a1,
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10),
              v7(a1, &GUID_00000036_0000_0000_c000_000000000046, &v10) >= 0) )
        {
          (*(void (__fastcall **)(__int64, HRESULT *))(*(_QWORD *)v10 + 64LL))(v10, &v11);
        }
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
      v4 = v11;
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[2])(a1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180042638  mov     [rsp-18h+dwindex], r8
0x18004263d  mov     [rsp-18h+arg_8], edx
0x180042641  push    rbp
0x180042642  push    rbx
0x180042643  push    rdi
0x180042644  mov     rbp, rsp
0x180042647  sub     rsp, 50h
0x18004264b  mov     rdi, rcx
0x18004264e  mov     [rbp+var_20], rcx
0x180042652  test    rcx, rcx
0x180042655  jz      short loc_180042664
0x180042657  mov     rax, [rcx]
0x18004265a  mov     rax, [rax+8]
0x18004265e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042663  nop
0x180042664  mov     [rbp+arg_18], 0
0x18004266c  lea     rcx, [rbp+arg_18]
0x180042670  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180042675  lea     rcx, [rbp+arg_18]
0x180042679  call    ??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)
0x18004267e  mov     ebx, eax
0x180042680  mov     [rbp+arg_8], eax
0x180042683  test    eax, eax
0x180042685  js      loc_1800427A4
0x18004268b  mov     rax, [rdi]
0x18004268e  mov     rdx, [rbp+arg_18]
0x180042692  mov     rcx, rdi
0x180042695  mov     rax, [rax+30h]
0x180042699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004269e  mov     ebx, eax
0x1800426a0  mov     [rbp+arg_8], eax
0x1800426a3  test    eax, eax
0x1800426a5  js      loc_1800427A4
0x1800426ab  mov     rax, [rbp+arg_18]
0x1800426af  mov     rcx, [rax+38h]
0x1800426b3  mov     [rbp+pHandles], rcx
0x1800426b7  mov     [rbp+var_10], 0
0x1800426bf  xor     bl, bl
0x1800426c1  mov     dword ptr [rbp+dwindex], 0
0x1800426c8  lea     rax, [rbp+dwindex]
0x1800426cc  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x1800426d1  lea     r9, [rbp+pHandles]; pHandles
0x1800426d5  mov     r8d, 1; cHandles
0x1800426db  or      edx, 0FFFFFFFFh; dwTimeout
0x1800426de  lea     ecx, [r8+7]; dwFlags
0x1800426e2  call    cs:__imp_CoWaitForMultipleHandles
0x1800426e8  mov     [rbp+arg_8], eax
0x1800426eb  test    eax, eax
0x1800426ed  js      short loc_1800426FE
0x1800426ef  cmp     dword ptr [rbp+dwindex], 0
0x1800426f3  jz      short loc_1800426FE
0x1800426f5  mov     [rbp+arg_8], 800704C7h
0x1800426fc  mov     bl, 1
0x1800426fe  mov     [rbp+arg_0], 0
0x180042706  test    bl, bl
0x180042708  jz      short loc_180042743
0x18004270a  mov     rax, [rdi]
0x18004270d  mov     rbx, [rax]
0x180042710  lea     rcx, [rbp+arg_0]
0x180042714  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180042719  lea     r8, [rbp+arg_0]
0x18004271d  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180042724  mov     rcx, rdi
0x180042727  mov     rax, rbx
0x18004272a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004272f  test    eax, eax
0x180042731  js      short loc_180042743
0x180042733  mov     rcx, [rbp+arg_0]
0x180042737  mov     rax, [rcx]
0x18004273a  mov     rax, [rax+48h]
0x18004273e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042743  cmp     [rbp+arg_8], 0
0x180042747  jl      short loc_180042798
0x180042749  mov     rax, [rbp+arg_18]
0x18004274d  cmp     dword ptr [rax+30h], 1
0x180042751  jz      short loc_180042798
0x180042753  cmp     [rbp+arg_0], 0
0x180042758  jnz     short loc_180042783
0x18004275a  mov     rax, [rdi]
0x18004275d  mov     rbx, [rax]
0x180042760  lea     rcx, [rbp+arg_0]
0x180042764  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180042769  lea     r8, [rbp+arg_0]
0x18004276d  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180042774  mov     rcx, rdi
0x180042777  mov     rax, rbx
0x18004277a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004277f  test    eax, eax
0x180042781  js      short loc_180042798
0x180042783  mov     rcx, [rbp+arg_0]
0x180042787  mov     rax, [rcx]
0x18004278a  lea     rdx, [rbp+arg_8]
0x18004278e  mov     rax, [rax+40h]
0x180042792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042797  nop
0x180042798  lea     rcx, [rbp+arg_0]
0x18004279c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800427a1  mov     ebx, [rbp+arg_8]
0x1800427a4  lea     rcx, [rbp+arg_18]
0x1800427a8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800427ad  nop
0x1800427ae  test    rdi, rdi
0x1800427b1  jz      short loc_1800427C3
0x1800427b3  mov     rcx, [rdi]
0x1800427b6  mov     rax, [rcx+10h]
0x1800427ba  mov     rcx, rdi
0x1800427bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800427c2  nop
0x1800427c3  mov     eax, ebx
0x1800427c5  add     rsp, 50h
0x1800427c9  pop     rdi
0x1800427ca  pop     rbx
0x1800427cb  pop     rbp
0x1800427cc  retn
```
