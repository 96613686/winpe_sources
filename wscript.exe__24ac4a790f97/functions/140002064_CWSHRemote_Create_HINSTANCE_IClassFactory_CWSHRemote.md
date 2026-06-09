# CWSHRemote::Create(HINSTANCE__ *,IClassFactory *,CWSHRemote * *)

- ea: `0x140002064`
- end: `0x140002234`
- name: `?Create@CWSHRemote@@SAJPEAUHINSTANCE__@@PEAUIClassFactory@@PEAPEAV1@@Z`
- size: `464`
- prototype: `static int(HINSTANCE, struct IClassFactory *, struct CWSHRemote **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001c60`

## callees

- `0x140001008`
- `0x140001488`
- `0x140001564`
- `0x140002064`
- `0x14001755a`
- `0x140018010`

## import_xrefs

- `OLEAUT32!__imp_LoadRegTypeLib` at `0x140002164`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x140002164`
- `KERNEL32!GetCurrentThreadId` at `0x1400020cf`
- `KERNEL32!GetCurrentThreadId` at `0x14000210d`
- `KERNEL32!GetCurrentThreadId` at `0x1400020cf`
- `KERNEL32!GetCurrentThreadId` at `0x14000210d`

## pseudocode

```c
__int64 __fastcall CWSHRemote::Create(HINSTANCE a1, struct IClassFactory *a2, struct CWSHRemote **a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rdi
  DWORD CurrentThreadId; // eax
  HRESULT v9; // ebx
  ITypeLib *pptlib; // [rsp+80h] [rbp+18h] BYREF

  pptlib = 0;
  *a3 = 0;
  v6 = operator new(0x240u);
  v7 = v6;
  if ( !v6 )
  {
    v9 = -2147024882;
    goto LABEL_8;
  }
  v6[4] = 1;
  *v6 = &CWSHRemote::`vftable'{for `IWSHRemote'};
  v6[1] = &CWSHRemote::`vftable'{for `IProvideClassInfo'};
  v6[2] = &CWSHRemote::`vftable'{for `IConnectionPointContainer'};
  v6[3] = &CWSHRemote::`vftable'{for `IConnectionPoint'};
  CurrentThreadId = GetCurrentThreadId();
  *((_DWORD *)v7 + 11) = 0;
  *((_DWORD *)v7 + 10) = CurrentThreadId;
  *((_WORD *)v7 + 28) = 0;
  v7[8] = 0;
  v7[9] = 0;
  v7[10] = 0;
  v7[11] = 0;
  v7[12] = 0;
  v7[13] = 0;
  v7[14] = 0;
  CCriticalSection::CCriticalSection((CCriticalSection *)(v7 + 15));
  *((_DWORD *)v7 + 142) = 0;
  *((_DWORD *)v7 + 143) = GetCurrentThreadId();
  memset_0(v7 + 21, 0, 0x190u);
  v9 = CWSHRemote::CError::Create(a2, (struct CWSHRemote::CError **)v7 + 8);
  if ( v9 >= 0 )
  {
    v9 = LoadRegTypeLib(&LIBID_WSHRemoteLibrary, 1u, 0, 0x409u, &pptlib);
    if ( v9 >= 0 )
    {
      v9 = ((__int64 (__fastcall *)(ITypeLib *, GUID *, _QWORD *))pptlib->lpVtbl->GetTypeInfoOfGuid)(
             pptlib,
             &IID_IWSHRemote,
             v7 + 9);
      if ( v9 >= 0 )
      {
        v9 = ((__int64 (__fastcall *)(ITypeLib *, GUID *, _QWORD *))pptlib->lpVtbl->GetTypeInfoOfGuid)(
               pptlib,
               &CLSID_WSHRemote,
               v7 + 10);
        if ( v9 >= 0 )
        {
          v7[11] = a2;
          ((void (__fastcall *)(struct IClassFactory *))a2->lpVtbl->AddRef)(a2);
          ((void (__fastcall *)(struct IClassFactory *, __int64))a2->lpVtbl->LockServer)(a2, 1);
          v7[6] = a1;
          v9 = 0;
          *a3 = (struct CWSHRemote *)v7;
LABEL_8:
          v7 = 0;
        }
      }
    }
  }
  if ( pptlib )
    ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
  if ( v7 )
    (*(void (__fastcall **)(_QWORD *))(*v7 + 16LL))(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140002064  mov     rax, rsp
0x140002067  push    rbx
0x140002068  push    rbp
0x140002069  push    rsi
0x14000206a  push    rdi
0x14000206b  push    r14
0x14000206d  push    r15
0x14000206f  sub     rsp, 38h
0x140002073  mov     rbp, rcx
0x140002076  xor     r15d, r15d
0x140002079  mov     ecx, 240h; Size
0x14000207e  mov     [rax+18h], r15
0x140002082  mov     [r8], r15
0x140002085  mov     r14, r8
0x140002088  mov     rsi, rdx
0x14000208b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140002090  mov     rdi, rax
0x140002093  test    rax, rax
0x140002096  jz      loc_1400021F0
0x14000209c  lea     rax, ??_7CWSHRemote@@6BIWSHRemote@@@; const CWSHRemote::`vftable'{for `IWSHRemote'}
0x1400020a3  mov     qword ptr [rdi+20h], 1
0x1400020ab  mov     [rdi], rax
0x1400020ae  lea     rax, ??_7CWSHRemote@@6BIProvideClassInfo@@@; const CWSHRemote::`vftable'{for `IProvideClassInfo'}
0x1400020b5  mov     [rdi+8], rax
0x1400020b9  lea     rax, ??_7CWSHRemote@@6BIConnectionPointContainer@@@; const CWSHRemote::`vftable'{for `IConnectionPointContainer'}
0x1400020c0  mov     [rdi+10h], rax
0x1400020c4  lea     rax, ??_7CWSHRemote@@6BIConnectionPoint@@@; const CWSHRemote::`vftable'{for `IConnectionPoint'}
0x1400020cb  mov     [rdi+18h], rax
0x1400020cf  call    cs:__imp_GetCurrentThreadId
0x1400020d5  lea     rcx, [rdi+78h]; this
0x1400020d9  mov     [rdi+2Ch], r15d
0x1400020dd  mov     [rdi+28h], eax
0x1400020e0  mov     [rdi+38h], r15w
0x1400020e5  mov     [rdi+40h], r15
0x1400020e9  mov     [rdi+48h], r15
0x1400020ed  mov     [rdi+50h], r15
0x1400020f1  mov     [rdi+58h], r15
0x1400020f5  mov     [rdi+60h], r15
0x1400020f9  mov     [rdi+68h], r15
0x1400020fd  mov     [rdi+70h], r15
0x140002101  call    ??0CCriticalSection@@QEAA@XZ; CCriticalSection::CCriticalSection(void)
0x140002106  mov     [rdi+238h], r15d
0x14000210d  call    cs:__imp_GetCurrentThreadId
0x140002113  xor     edx, edx; Val
0x140002115  lea     rcx, [rdi+0A8h]; void *
0x14000211c  mov     r8d, 190h; Size
0x140002122  mov     [rdi+23Ch], eax
0x140002128  call    memset_0
0x14000212d  lea     rdx, [rdi+40h]; struct CWSHRemote::CError **
0x140002131  mov     rcx, rsi; struct IClassFactory *
0x140002134  call    ?Create@CError@CWSHRemote@@SAJPEAUIClassFactory@@PEAPEAV12@@Z; CWSHRemote::CError::Create(IClassFactory *,CWSHRemote::CError * *)
0x140002139  mov     ebx, eax
0x14000213b  test    eax, eax
0x14000213d  js      loc_1400021F8
0x140002143  lea     rax, [rsp+68h+arg_10]
0x14000214b  xor     r8d, r8d; wVerMinor
0x14000214e  lea     edx, [r15+1]; wVerMajor
0x140002152  mov     [rsp+68h+pptlib], rax; pptlib
0x140002157  mov     r9d, 409h; lcid
0x14000215d  lea     rcx, LIBID_WSHRemoteLibrary; rguid
0x140002164  call    cs:__imp_LoadRegTypeLib
0x14000216a  mov     ebx, eax
0x14000216c  test    eax, eax
0x14000216e  js      loc_1400021F8
0x140002174  mov     rcx, [rsp+68h+arg_10]
0x14000217c  lea     r8, [rdi+48h]
0x140002180  lea     rdx, IID_IWSHRemote
0x140002187  mov     rax, [rcx]
0x14000218a  mov     rax, [rax+30h]
0x14000218e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002193  mov     ebx, eax
0x140002195  test    eax, eax
0x140002197  js      short loc_1400021F8
0x140002199  mov     rcx, [rsp+68h+arg_10]
0x1400021a1  lea     r8, [rdi+50h]
0x1400021a5  lea     rdx, CLSID_WSHRemote
0x1400021ac  mov     rax, [rcx]
0x1400021af  mov     rax, [rax+30h]
0x1400021b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400021b8  mov     ebx, eax
0x1400021ba  test    eax, eax
0x1400021bc  js      short loc_1400021F8
0x1400021be  mov     [rdi+58h], rsi
0x1400021c2  mov     rcx, rsi
0x1400021c5  mov     rax, [rsi]
0x1400021c8  mov     rax, [rax+8]
0x1400021cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400021d1  mov     rax, [rsi]
0x1400021d4  lea     edx, [r15+1]
0x1400021d8  mov     rcx, rsi
0x1400021db  mov     rax, [rax+20h]
0x1400021df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400021e4  mov     [rdi+30h], rbp
0x1400021e8  mov     ebx, r15d
0x1400021eb  mov     [r14], rdi
0x1400021ee  jmp     short loc_1400021F5
0x1400021f0  mov     ebx, 8007000Eh
0x1400021f5  mov     rdi, r15
0x1400021f8  mov     rcx, [rsp+68h+arg_10]
0x140002200  test    rcx, rcx
0x140002203  jz      short loc_140002211
0x140002205  mov     rax, [rcx]
0x140002208  mov     rax, [rax+10h]
0x14000220c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002211  test    rdi, rdi
0x140002214  jz      short loc_140002225
0x140002216  mov     rax, [rdi]
0x140002219  mov     rcx, rdi
0x14000221c  mov     rax, [rax+10h]
0x140002220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002225  mov     eax, ebx
0x140002227  add     rsp, 38h
0x14000222b  pop     r15
0x14000222d  pop     r14
0x14000222f  pop     rdi
0x140002230  pop     rsi
0x140002231  pop     rbp
0x140002232  pop     rbx
0x140002233  retn
```
