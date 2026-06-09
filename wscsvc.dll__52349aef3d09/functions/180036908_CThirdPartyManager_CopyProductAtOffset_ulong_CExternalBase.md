# CThirdPartyManager::CopyProductAtOffset(ulong,CExternalBase * *)

- ea: `0x180036908`
- end: `0x180036a27`
- name: `?CopyProductAtOffset@CThirdPartyManager@@QEAAJKPEAPEAVCExternalBase@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(CThirdPartyManager *__hidden this, unsigned int, struct CExternalBase **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18002fc00`

## callees

- `0x180009f40`
- `0x18000b3d0`
- `0x180018b20`
- `0x180036908`
- `0x180037688`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800369f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800369f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003694d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003694d`

## pseudocode

```c
__int64 __fastcall CThirdPartyManager::CopyProductAtOffset(
        CThirdPartyManager *this,
        unsigned int a2,
        struct CExternalBase **a3)
{
  CThirdPartyManager *v6; // rdi
  __int64 v7; // r9
  int v8; // r10d
  __int64 Next; // r14
  int v10; // ebx
  CExternalBase *v11; // [rsp+40h] [rbp+8h] BYREF
  __int64 HeadPosition; // [rsp+50h] [rbp+18h] BYREF

  v11 = 0;
  if ( !a3 )
    return 2147942487LL;
  v6 = WscServiceUtils::g_pAntiVirusManager;
  *a3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 16));
  if ( a2 >= *(_DWORD *)(*((_QWORD *)v6 + 7) + 48LL) )
  {
    v10 = -2147024809;
  }
  else
  {
    HeadPosition = CList<unsigned short *,unsigned short *>::GetHeadPosition(*((_QWORD *)v6 + 7));
    if ( HeadPosition )
    {
      do
        Next = CList<CExternalBase *,CExternalBase *>::GetNext(v7, &HeadPosition);
      while ( v8 + 1 <= a2 );
      v10 = (*(__int64 (__fastcall **)(CThirdPartyManager *, CExternalBase **))(*(_QWORD *)v6 + 40LL))(v6, &v11);
      if ( v10 >= 0 )
      {
        v10 = CExternalBase::Initialize(v11, *(const unsigned __int16 **)(Next + 8));
        if ( v10 >= 0 )
        {
          v10 = CThirdPartyManager::PopulateProductInformation(v6, v11);
          if ( v10 >= 0 )
          {
            *a3 = v11;
            v11 = 0;
          }
        }
      }
    }
    else
    {
      v10 = -2147467259;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 16));
  if ( v11 )
    (**(void (__fastcall ***)(CExternalBase *, __int64))v11)(v11, 1);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180036908  mov     rax, rsp
0x18003690b  mov     [rax+10h], rbx
0x18003690f  mov     [rax+20h], rbp
0x180036913  mov     [rax+8], rcx
0x180036917  push    rsi
0x180036918  push    rdi
0x180036919  push    r14
0x18003691b  sub     rsp, 20h
0x18003691f  mov     qword ptr [rax+8], 0
0x180036927  mov     rsi, r8
0x18003692a  mov     ebx, edx
0x18003692c  test    r8, r8
0x18003692f  jnz     short loc_18003693B
0x180036931  mov     eax, 80070057h
0x180036936  jmp     loc_180036A14
0x18003693b  mov     rdi, cs:?g_pAntiVirusManager@WscServiceUtils@@3PEAVCAntiVirusManager@@EA; CAntiVirusManager * WscServiceUtils::g_pAntiVirusManager
0x180036942  mov     qword ptr [r8], 0
0x180036949  lea     rcx, [rdi+10h]; lpCriticalSection
0x18003694d  call    cs:__imp_EnterCriticalSection
0x180036953  mov     r9, [rdi+38h]
0x180036957  cmp     ebx, [r9+30h]
0x18003695b  jnb     loc_1800369E9
0x180036961  mov     rcx, r9
0x180036964  call    ?GetHeadPosition@?$CList@PEAGPEAG@@QEBAPEAU_CListElement@@XZ; CList<ushort *,ushort *>::GetHeadPosition(void)
0x180036969  mov     [rsp+38h+arg_10], rax
0x18003696e  test    rax, rax
0x180036971  jz      short loc_1800369E2
0x180036973  xor     r10d, r10d
0x180036976  lea     rdx, [rsp+38h+arg_10]
0x18003697b  mov     rcx, r9
0x18003697e  call    ?GetNext@?$CList@PEAVCExternalBase@@PEAV1@@@QEAAPEAVCExternalBase@@AEAPEAU_CListElement@@@Z; CList<CExternalBase *,CExternalBase *>::GetNext(_CListElement * &)
0x180036983  inc     r10d
0x180036986  mov     r14, rax
0x180036989  cmp     r10d, ebx
0x18003698c  jbe     short loc_180036976
0x18003698e  mov     rcx, [rdi]
0x180036991  lea     rdx, [rsp+38h+arg_0]
0x180036996  mov     rax, [rcx+28h]
0x18003699a  mov     rcx, rdi
0x18003699d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369a2  mov     ebx, eax
0x1800369a4  test    eax, eax
0x1800369a6  js      short loc_1800369EE
0x1800369a8  mov     rdx, [r14+8]; unsigned __int16 *
0x1800369ac  mov     rcx, [rsp+38h+arg_0]; this
0x1800369b1  call    ?Initialize@CExternalBase@@QEAAJPEBG@Z; CExternalBase::Initialize(ushort const *)
0x1800369b6  mov     ebx, eax
0x1800369b8  test    eax, eax
0x1800369ba  js      short loc_1800369EE
0x1800369bc  mov     rdx, [rsp+38h+arg_0]; struct CExternalBase *
0x1800369c1  mov     rcx, rdi; this
0x1800369c4  call    ?PopulateProductInformation@CThirdPartyManager@@QEAAJPEAVCExternalBase@@@Z; CThirdPartyManager::PopulateProductInformation(CExternalBase *)
0x1800369c9  mov     ebx, eax
0x1800369cb  test    eax, eax
0x1800369cd  js      short loc_1800369EE
0x1800369cf  mov     rax, [rsp+38h+arg_0]
0x1800369d4  mov     [rsi], rax
0x1800369d7  mov     [rsp+38h+arg_0], 0
0x1800369e0  jmp     short loc_1800369EE
0x1800369e2  mov     ebx, 80004005h
0x1800369e7  jmp     short loc_1800369EE
0x1800369e9  mov     ebx, 80070057h
0x1800369ee  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800369f2  call    cs:__imp_LeaveCriticalSection
0x1800369f8  mov     rcx, [rsp+38h+arg_0]
0x1800369fd  test    rcx, rcx
0x180036a00  jz      short loc_180036A12
0x180036a02  mov     rax, [rcx]
0x180036a05  mov     edx, 1
0x180036a0a  mov     rax, [rax]
0x180036a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a12  mov     eax, ebx
0x180036a14  mov     rbx, [rsp+38h+arg_8]
0x180036a19  mov     rbp, [rsp+38h+arg_18]
0x180036a1e  add     rsp, 20h
0x180036a22  pop     r14
0x180036a24  pop     rdi
0x180036a25  pop     rsi
0x180036a26  retn
```
