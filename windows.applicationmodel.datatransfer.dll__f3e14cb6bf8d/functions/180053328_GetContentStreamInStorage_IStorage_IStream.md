# _GetContentStreamInStorage(IStorage *,IStream * *)

- ea: `0x180053328`
- end: `0x180053511`
- name: `?_GetContentStreamInStorage@@YAJPEAUIStorage@@PEAPEAUIStream@@@Z`
- size: `489`
- prototype: `__int64 __fastcall(struct IStorage *, struct IStream **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180052598`

## callees

- `0x180002ad0`
- `0x18000346c`
- `0x180053328`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180053425`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180053425`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800534e5`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800534e5`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180053362`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180053362`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x18005338f`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x18005338f`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x1800533b7`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x1800533b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _GetContentStreamInStorage(struct IStorage *a1, struct IStream **a2)
{
  HGLOBAL v4; // rax
  void *v5; // rbx
  HRESULT v6; // edi
  LPSTREAM v7; // rcx
  IStorage *v8; // rcx
  LPLOCKBYTES v9; // rcx
  LPSTREAM ppstm; // [rsp+30h] [rbp-39h] BYREF
  IStorage *ppstgOpen; // [rsp+38h] [rbp-31h] BYREF
  LPLOCKBYTES pplkbyt; // [rsp+40h] [rbp-29h] BYREF
  HGLOBAL v14; // [rsp+48h] [rbp-21h]
  _BYTE v15[16]; // [rsp+50h] [rbp-19h] BYREF
  __int64 v16; // [rsp+60h] [rbp-9h]

  *a2 = 0;
  v4 = GlobalAlloc(2u, 0);
  v5 = v4;
  v14 = v4;
  if ( v4 )
  {
    pplkbyt = 0;
    v6 = CreateILockBytesOnHGlobal(v4, 0, &pplkbyt);
    if ( v6 >= 0 )
    {
      ppstgOpen = 0;
      v6 = StgCreateDocfileOnILockBytes(pplkbyt, 0x1012u, 0, &ppstgOpen);
      if ( v6 >= 0 )
      {
        v6 = ((__int64 (__fastcall *)(struct IStorage *, _QWORD, _QWORD, _QWORD, IStorage *))a1->lpVtbl->CopyTo)(
               a1,
               0,
               0,
               0,
               ppstgOpen);
        if ( v6 >= 0 )
        {
          v6 = ((__int64 (__fastcall *)(IStorage *, _QWORD))ppstgOpen->lpVtbl->Commit)(ppstgOpen, 0);
          if ( v6 >= 0 )
          {
            ppstm = 0;
            v6 = CreateStreamOnHGlobal(v5, 1, &ppstm);
            if ( v6 < 0
              || (v5 = 0,
                  v14 = 0,
                  memset_0(v15, 0, 0x50u),
                  v6 = ((__int64 (__fastcall *)(LPLOCKBYTES, _BYTE *, __int64))pplkbyt->lpVtbl->Stat)(pplkbyt, v15, 1),
                  v6 < 0)
              || (v6 = (*(__int64 (__fastcall **)(LPSTREAM, __int64))(*(_QWORD *)ppstm + 48LL))(ppstm, v16), v6 < 0) )
            {
              v7 = ppstm;
            }
            else
            {
              v7 = 0;
              *a2 = ppstm;
            }
            if ( v7 )
            {
              ppstm = 0;
              (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v7 + 16LL))(v7);
            }
          }
        }
      }
      v8 = ppstgOpen;
      if ( ppstgOpen )
      {
        ppstgOpen = 0;
        ((void (__fastcall *)(IStorage *))v8->lpVtbl->Release)(v8);
      }
    }
    v9 = pplkbyt;
    if ( pplkbyt )
    {
      pplkbyt = 0;
      ((void (__fastcall *)(LPLOCKBYTES))v9->lpVtbl->Release)(v9);
    }
  }
  else
  {
    v6 = -2147024882;
  }
  GlobalFree(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180053328  mov     [rsp-8+arg_10], rbx
0x18005332d  mov     [rsp-8+arg_18], rsi
0x180053332  push    rbp
0x180053333  push    rdi
0x180053334  push    r14
0x180053336  lea     rbp, [rsp-47h]
0x18005333b  sub     rsp, 0B0h
0x180053342  mov     rax, cs:__security_cookie
0x180053349  xor     rax, rsp
0x18005334c  mov     [rbp+57h+var_20], rax
0x180053350  mov     rsi, rdx
0x180053353  mov     r14, rcx
0x180053356  mov     qword ptr [rdx], 0
0x18005335d  xor     edx, edx; dwBytes
0x18005335f  lea     ecx, [rdx+2]; uFlags
0x180053362  call    cs:__imp_GlobalAlloc
0x180053368  mov     rbx, rax
0x18005336b  mov     [rbp+57h+var_78], rax
0x18005336f  test    rax, rax
0x180053372  jnz     short loc_18005337E
0x180053374  mov     edi, 8007000Eh
0x180053379  jmp     loc_1800534E2
0x18005337e  mov     [rbp+57h+pplkbyt], 0
0x180053386  lea     r8, [rbp+57h+pplkbyt]; pplkbyt
0x18005338a  xor     edx, edx; fDeleteOnRelease
0x18005338c  mov     rcx, rbx; hGlobal
0x18005338f  call    cs:__imp_CreateILockBytesOnHGlobal
0x180053395  mov     edi, eax
0x180053397  test    eax, eax
0x180053399  js      loc_1800534C4
0x18005339f  mov     [rbp+57h+ppstgOpen], 0
0x1800533a7  lea     r9, [rbp+57h+ppstgOpen]; ppstgOpen
0x1800533ab  xor     r8d, r8d; reserved
0x1800533ae  mov     edx, 1012h; grfMode
0x1800533b3  mov     rcx, [rbp+57h+pplkbyt]; plkbyt
0x1800533b7  call    cs:__imp_StgCreateDocfileOnILockBytes
0x1800533bd  mov     edi, eax
0x1800533bf  test    eax, eax
0x1800533c1  js      loc_1800534A6
0x1800533c7  mov     rdx, [rbp+57h+ppstgOpen]
0x1800533cb  mov     rax, [r14]
0x1800533ce  mov     [rsp+0C0h+var_A0], rdx
0x1800533d3  xor     r9d, r9d
0x1800533d6  xor     r8d, r8d
0x1800533d9  xor     edx, edx
0x1800533db  mov     rcx, r14
0x1800533de  mov     rax, [rax+38h]
0x1800533e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800533e7  mov     edi, eax
0x1800533e9  test    eax, eax
0x1800533eb  js      loc_1800534A6
0x1800533f1  mov     rcx, [rbp+57h+ppstgOpen]
0x1800533f5  mov     rax, [rcx]
0x1800533f8  xor     edx, edx
0x1800533fa  mov     rax, [rax+48h]
0x1800533fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053403  mov     edi, eax
0x180053405  test    eax, eax
0x180053407  js      loc_1800534A6
0x18005340d  mov     [rbp+57h+ppstm], 0
0x180053415  lea     r8, [rbp+57h+ppstm]; ppstm
0x180053419  mov     r14d, 1
0x18005341f  mov     edx, r14d; fDeleteOnRelease
0x180053422  mov     rcx, rbx; hGlobal
0x180053425  call    cs:__imp_CreateStreamOnHGlobal
0x18005342b  mov     edi, eax
0x18005342d  test    eax, eax
0x18005342f  js      short loc_180053488
0x180053431  xor     ebx, ebx
0x180053433  mov     [rbp+57h+var_78], rbx
0x180053437  xor     edx, edx; Val
0x180053439  lea     r8d, [r14+4Fh]; Size
0x18005343d  lea     rcx, [rbp+57h+var_70]; void *
0x180053441  call    memset_0
0x180053446  mov     rcx, [rbp+57h+pplkbyt]
0x18005344a  mov     rax, [rcx]
0x18005344d  mov     r8d, r14d
0x180053450  lea     rdx, [rbp+57h+var_70]
0x180053454  mov     rax, [rax+48h]
0x180053458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005345d  mov     edi, eax
0x18005345f  test    eax, eax
0x180053461  js      short loc_180053488
0x180053463  mov     rcx, [rbp+57h+ppstm]
0x180053467  mov     rax, [rcx]
0x18005346a  mov     rdx, [rbp+57h+var_60]
0x18005346e  mov     rax, [rax+30h]
0x180053472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053477  mov     edi, eax
0x180053479  test    eax, eax
0x18005347b  js      short loc_180053488
0x18005347d  mov     rax, [rbp+57h+ppstm]
0x180053481  xor     ecx, ecx
0x180053483  mov     [rsi], rax
0x180053486  jmp     short loc_18005348C
0x180053488  mov     rcx, [rbp+57h+ppstm]
0x18005348c  test    rcx, rcx
0x18005348f  jz      short loc_1800534A6
0x180053491  mov     [rbp+57h+ppstm], 0
0x180053499  mov     rax, [rcx]
0x18005349c  mov     rax, [rax+10h]
0x1800534a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800534a5  nop
0x1800534a6  mov     rcx, [rbp+57h+ppstgOpen]
0x1800534aa  test    rcx, rcx
0x1800534ad  jz      short loc_1800534C4
0x1800534af  mov     [rbp+57h+ppstgOpen], 0
0x1800534b7  mov     rax, [rcx]
0x1800534ba  mov     rax, [rax+10h]
0x1800534be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800534c3  nop
0x1800534c4  mov     rcx, [rbp+57h+pplkbyt]
0x1800534c8  test    rcx, rcx
0x1800534cb  jz      short loc_1800534E2
0x1800534cd  mov     [rbp+57h+pplkbyt], 0
0x1800534d5  mov     rax, [rcx]
0x1800534d8  mov     rax, [rax+10h]
0x1800534dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800534e1  nop
0x1800534e2  mov     rcx, rbx; hMem
0x1800534e5  call    cs:__imp_GlobalFree
0x1800534eb  mov     eax, edi
0x1800534ed  mov     rcx, [rbp+57h+var_20]
0x1800534f1  xor     rcx, rsp; StackCookie
0x1800534f4  call    __security_check_cookie
0x1800534f9  lea     r11, [rsp+0C0h+var_10]
0x180053501  mov     rbx, [r11+30h]
0x180053505  mov     rsi, [r11+38h]
0x180053509  mov     rsp, r11
0x18005350c  pop     r14
0x18005350e  pop     rdi
0x18005350f  pop     rbp
0x180053510  retn
```
