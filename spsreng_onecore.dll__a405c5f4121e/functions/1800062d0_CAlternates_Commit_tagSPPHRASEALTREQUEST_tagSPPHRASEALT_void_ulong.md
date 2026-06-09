# CAlternates::Commit(tagSPPHRASEALTREQUEST *,tagSPPHRASEALT *,void * *,ulong *)

- ea: `0x1800062d0`
- end: `0x180006468`
- name: `?Commit@CAlternates@@UEAAJPEAUtagSPPHRASEALTREQUEST@@PEAUtagSPPHRASEALT@@PEAPEAXPEAK@Z`
- size: `408`
- prototype: `__int64 __fastcall(CAlternates *__hidden this, struct tagSPPHRASEALTREQUEST *, struct tagSPPHRASEALT *, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002db8`
- `0x180004312`
- `0x1800062d0`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006376`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006376`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAlternates::Commit(
        CAlternates *this,
        struct tagSPPHRASEALTREQUEST *a2,
        struct tagSPPHRASEALT *a3,
        void **a4,
        unsigned int *a5)
{
  unsigned int *v8; // rsi
  int v9; // r14d
  void *v10; // rax
  __int16 *pvAltExtra; // r8
  _WORD *v12; // r9
  char *v13; // r10
  unsigned int v14; // ecx
  __int16 v15; // ax
  __int64 v17; // [rsp+48h] [rbp+10h] BYREF

  v17 = 0;
  if ( a2 && a4 && (v8 = a5) != 0 && (a3->pvAltExtra || !a3->cbAltExtra) )
  {
    v9 = 0;
    if ( ((__int64 (__fastcall *)(ISpRecoContext *, GUID *, __int64 *))a2->pRecoContext->lpVtbl->QueryInterface)(
           a2->pRecoContext,
           &GUID_3d60d8ea_9295_4ff4_8f9d_262483efd47a,
           &v17) >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD))(*(_QWORD *)v17 + 360LL))(
             v17,
             a2->pvResultExtra,
             a2->cbResultExtra);
      if ( v9 >= 0 )
      {
        v10 = CoTaskMemAlloc(a2->cbResultExtra);
        *a4 = v10;
        if ( v10 )
        {
          memcpy_0(v10, a2->pvResultExtra, a2->cbResultExtra);
          *v8 = a2->cbResultExtra;
          pvAltExtra = (__int16 *)a3->pvAltExtra;
          if ( pvAltExtra )
          {
            v12 = *a4;
            v13 = (char *)*a4 + 116 * *((unsigned int *)*a4 + 10) + 40 * *((unsigned int *)*a4 + 11);
            v14 = 1;
            if ( *((_WORD *)*a4 + 25) )
            {
              do
              {
                if ( (v13[16 * v14 + 144] & 2) != 0 )
                {
                  v15 = *pvAltExtra;
                  pvAltExtra += 2;
                  *(_WORD *)&v13[16 * v14 + 148] = v15;
                }
                ++v14;
              }
              while ( v14 <= (unsigned __int16)v12[25] );
            }
            if ( (v12[32] & 1) == 0 )
              (*(void (__fastcall **)(__int64, struct tagSPPHRASEALTREQUEST *, struct tagSPPHRASEALT *))(*(_QWORD *)v17 + 200LL))(
                v17,
                a2,
                a3);
          }
        }
        else
        {
          *a4 = 0;
          *v8 = 0;
          v9 = -2147024882;
        }
      }
    }
    ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v17);
    return (unsigned int)v9;
  }
  else
  {
    ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v17);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800062d0  mov     [rsp+arg_0], rbx
0x1800062d5  mov     [rsp+arg_10], rbp
0x1800062da  push    rsi
0x1800062db  push    rdi
0x1800062dc  push    r14
0x1800062de  sub     rsp, 20h
0x1800062e2  mov     rdi, r9
0x1800062e5  mov     rbp, r8
0x1800062e8  mov     rbx, rdx
0x1800062eb  mov     [rsp+38h+arg_8], 0
0x1800062f4  test    rdx, rdx
0x1800062f7  jz      loc_180006446
0x1800062fd  test    r9, r9
0x180006300  jz      loc_180006446
0x180006306  mov     rsi, [rsp+38h+arg_20]
0x18000630b  test    rsi, rsi
0x18000630e  jz      loc_180006446
0x180006314  cmp     qword ptr [r8+18h], 0
0x180006319  jnz     short loc_180006326
0x18000631b  cmp     dword ptr [r8+20h], 0
0x180006320  jnz     loc_180006446
0x180006326  xor     r14d, r14d
0x180006329  mov     rcx, [rdx+28h]
0x18000632d  mov     rax, [rcx]
0x180006330  lea     r8, [rsp+38h+arg_8]
0x180006335  lea     rdx, _GUID_3d60d8ea_9295_4ff4_8f9d_262483efd47a
0x18000633c  mov     rax, [rax]
0x18000633f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006344  test    eax, eax
0x180006346  js      loc_180006437
0x18000634c  mov     rcx, [rsp+38h+arg_8]
0x180006351  mov     rax, [rcx]
0x180006354  mov     r8d, [rbx+18h]
0x180006358  mov     rdx, [rbx+10h]
0x18000635c  mov     rax, [rax+168h]
0x180006363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006368  mov     r14d, eax
0x18000636b  test    eax, eax
0x18000636d  js      loc_180006437
0x180006373  mov     ecx, [rbx+18h]; cb
0x180006376  call    cs:__imp_CoTaskMemAlloc
0x18000637c  mov     [rdi], rax
0x18000637f  test    rax, rax
0x180006382  jz      loc_180006424
0x180006388  mov     r8d, [rbx+18h]; Size
0x18000638c  mov     rdx, [rbx+10h]; Src
0x180006390  mov     rcx, rax; void *
0x180006393  call    memcpy_0
0x180006398  mov     eax, [rbx+18h]
0x18000639b  mov     [rsi], eax
0x18000639d  mov     r8, [rbp+18h]
0x1800063a1  test    r8, r8
0x1800063a4  jz      loc_180006437
0x1800063aa  mov     r9, [rdi]
0x1800063ad  mov     eax, [r9+28h]
0x1800063b1  imul    rdx, rax, 74h ; 't'
0x1800063b5  mov     eax, [r9+2Ch]
0x1800063b9  lea     rcx, [rax+rax*4]
0x1800063bd  lea     rax, [r9+rdx]
0x1800063c1  lea     r10, [rax+rcx*8]
0x1800063c5  mov     r11d, 1
0x1800063cb  mov     ecx, r11d
0x1800063ce  cmp     r11w, [r9+32h]
0x1800063d3  ja      short loc_180006402
0x1800063d5  lea     eax, [rcx+rcx]
0x1800063d8  mov     edx, eax
0x1800063da  test    byte ptr [r10+rax*8+90h], 2
0x1800063e3  jz      short loc_1800063F6
0x1800063e5  movzx   eax, word ptr [r8]
0x1800063e9  add     r8, 4
0x1800063ed  mov     [r10+rdx*8+94h], ax
0x1800063f6  add     ecx, r11d
0x1800063f9  movzx   eax, word ptr [r9+32h]
0x1800063fe  cmp     ecx, eax
0x180006400  jbe     short loc_1800063D5
0x180006402  test    [r9+40h], r11b
0x180006406  jnz     short loc_180006437
0x180006408  mov     rcx, [rsp+38h+arg_8]
0x18000640d  mov     rax, [rcx]
0x180006410  mov     r8, rbp
0x180006413  mov     rdx, rbx
0x180006416  mov     rax, [rax+0C8h]
0x18000641d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006422  jmp     short loc_180006437
0x180006424  mov     qword ptr [rdi], 0
0x18000642b  mov     dword ptr [rsi], 0
0x180006431  mov     r14d, 8007000Eh
0x180006437  lea     rcx, [rsp+38h+arg_8]
0x18000643c  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x180006441  mov     eax, r14d
0x180006444  jmp     short loc_180006455
0x180006446  lea     rcx, [rsp+38h+arg_8]
0x18000644b  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x180006450  mov     eax, 80070057h
0x180006455  mov     rbx, [rsp+38h+arg_0]
0x18000645a  mov     rbp, [rsp+38h+arg_10]
0x18000645f  add     rsp, 20h
0x180006463  pop     r14
0x180006465  pop     rdi
0x180006466  pop     rsi
0x180006467  retn
```
