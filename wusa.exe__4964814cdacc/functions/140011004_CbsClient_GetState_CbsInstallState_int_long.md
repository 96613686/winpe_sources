# CbsClient::GetState(_CbsInstallState *,int *,long *)

- ea: `0x140011004`
- end: `0x14001116d`
- name: `?GetState@CbsClient@@QEAAJPEAW4_CbsInstallState@@PEAHPEAJ@Z`
- size: `361`
- prototype: `__int64 __fastcall(CbsClient *__hidden this, enum _CbsInstallState *, int *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14000afc0`

## callees

- `0x14000e280`
- `0x140011004`
- `0x140013490`
- `0x140015010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140011152`
- `KERNEL32!LocalFree` at `0x140011152`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011101`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011101`

## pseudocode

```c
__int64 __fastcall CbsClient::GetState(CbsClient *this, enum _CbsInstallState *a2, int *a3, int *a4)
{
  bool v4; // zf
  __int64 v8; // rcx
  signed int v9; // ebx
  int v10; // edx
  HLOCAL v11; // rdi
  LPVOID pv; // [rsp+30h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-8h] BYREF
  int v15; // [rsp+60h] [rbp+20h] BYREF
  int *v16; // [rsp+78h] [rbp+38h] BYREF

  v16 = a4;
  v4 = *(_QWORD *)this == 0;
  v15 = 0;
  LODWORD(v16) = 0;
  pv = 0;
  if ( v4 || (v8 = *((_QWORD *)this + 1)) == 0 )
  {
    v9 = -2147418113;
    WusaLogDebugEventA(L"CbsClient::GetState", 208, "CBS session is not initialized.");
  }
  else
  {
    v9 = (*(__int64 (__fastcall **)(__int64, int **, int *))(*(_QWORD *)v8 + 96LL))(v8, &v16, &v15);
    if ( v9 >= 0 )
    {
      if ( a2 )
        *(_DWORD *)a2 = (_DWORD)v16;
      if ( a3 )
      {
        v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, LPVOID *))(**((_QWORD **)this + 1) + 32LL))(
               *((_QWORD *)this + 1),
               11,
               &pv);
        if ( v9 >= 0 )
        {
          v10 = *(unsigned __int16 *)pv - 49;
          if ( *(_WORD *)pv == 49 )
            v10 = *((unsigned __int16 *)pv + 1);
          *a3 = v10 == 0;
        }
        else
        {
          WusaLogDebugEventA(L"CbsClient::GetState", 227, "Failed to query permanence property");
        }
      }
    }
    else
    {
      WusaLogDebugEventA(L"CbsClient::GetState", 212, "Failed to query status of package");
    }
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v9 < 0 )
  {
    hMem = 0;
    WusaGetErrorMessage(v9, (unsigned __int16 **)&hMem);
    v11 = hMem;
    WusaLogDebugEventA(L"CbsClient::GetState", 243, "Exit with error code 0X%x (%ls)", v9, (const wchar_t *)hMem);
    if ( v11 )
      LocalFree(v11);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140011004  mov     [rsp-18h+arg_8], rbx
0x140011009  mov     [rsp-18h+arg_10], rsi
0x14001100e  mov     [rsp-18h+arg_18], r9
0x140011013  push    rbp
0x140011014  push    rdi
0x140011015  push    r14
0x140011017  mov     rbp, rsp
0x14001101a  sub     rsp, 40h
0x14001101e  cmp     qword ptr [rcx], 0
0x140011022  mov     r14, r8
0x140011025  mov     rsi, rdx
0x140011028  mov     [rbp+arg_0], 0
0x14001102f  mov     rdi, rcx
0x140011032  mov     dword ptr [rbp+arg_18], 0
0x140011039  mov     [rbp+pv], 0
0x140011041  jz      loc_1400110DB
0x140011047  mov     rcx, [rcx+8]
0x14001104b  test    rcx, rcx
0x14001104e  jz      loc_1400110DB
0x140011054  mov     rax, [rcx]
0x140011057  lea     r8, [rbp+arg_0]
0x14001105b  lea     rdx, [rbp+arg_18]
0x14001105f  mov     rax, [rax+60h]
0x140011063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011068  mov     ebx, eax
0x14001106a  test    eax, eax
0x14001106c  jns     short loc_14001107C
0x14001106e  lea     r8, aFailedToQueryS; "Failed to query status of package"
0x140011075  mov     edx, 0D4h
0x14001107a  jmp     short loc_1400110EC
0x14001107c  test    rsi, rsi
0x14001107f  jz      short loc_140011086
0x140011081  mov     eax, dword ptr [rbp+arg_18]
0x140011084  mov     [rsi], eax
0x140011086  test    r14, r14
0x140011089  jz      short loc_1400110F8
0x14001108b  mov     rcx, [rdi+8]
0x14001108f  lea     r8, [rbp+pv]
0x140011093  mov     edx, 0Bh
0x140011098  mov     rax, [rcx]
0x14001109b  mov     rax, [rax+20h]
0x14001109f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400110a4  mov     ebx, eax
0x1400110a6  test    eax, eax
0x1400110a8  jns     short loc_1400110B8
0x1400110aa  lea     r8, aFailedToQueryP_0; "Failed to query permanence property"
0x1400110b1  mov     edx, 0E3h
0x1400110b6  jmp     short loc_1400110EC
0x1400110b8  mov     rcx, [rbp+pv]
0x1400110bc  movzx   edx, word ptr [rcx]
0x1400110bf  sub     edx, 31h ; '1'
0x1400110c2  jnz     short loc_1400110CF
0x1400110c4  movzx   edx, word ptr [rcx+2]
0x1400110c8  xor     eax, eax
0x1400110ca  movzx   ecx, ax
0x1400110cd  sub     edx, ecx
0x1400110cf  xor     eax, eax
0x1400110d1  test    edx, edx
0x1400110d3  setz    al
0x1400110d6  mov     [r14], eax
0x1400110d9  jmp     short loc_1400110F8
0x1400110db  mov     ebx, 8000FFFFh
0x1400110e0  lea     r8, aCbsSessionIsNo; "CBS session is not initialized."
0x1400110e7  mov     edx, 0D0h
0x1400110ec  lea     rcx, aCbsclientGetst; "CbsClient::GetState"
0x1400110f3  call    WusaLogDebugEventA
0x1400110f8  mov     rcx, [rbp+pv]; pv
0x1400110fc  test    rcx, rcx
0x1400110ff  jz      short loc_14001110F
0x140011101  call    cs:__imp_CoTaskMemFree
0x140011107  mov     [rbp+pv], 0
0x14001110f  test    ebx, ebx
0x140011111  jns     short loc_140011158
0x140011113  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x140011117  mov     [rbp+hMem], 0
0x14001111f  mov     ecx, ebx; dwMessageId
0x140011121  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x140011126  mov     rdi, [rbp+hMem]
0x14001112a  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x140011131  mov     r9d, ebx
0x140011134  mov     [rsp+40h+var_20], rdi
0x140011139  mov     edx, 0F3h
0x14001113e  lea     rcx, aCbsclientGetst; "CbsClient::GetState"
0x140011145  call    WusaLogDebugEventA
0x14001114a  test    rdi, rdi
0x14001114d  jz      short loc_140011158
0x14001114f  mov     rcx, rdi; hMem
0x140011152  call    cs:__imp_LocalFree
0x140011158  mov     rsi, [rsp+40h+arg_10]
0x14001115d  mov     eax, ebx
0x14001115f  mov     rbx, [rsp+40h+arg_8]
0x140011164  add     rsp, 40h
0x140011168  pop     r14
0x14001116a  pop     rdi
0x14001116b  pop     rbp
0x14001116c  retn
```
