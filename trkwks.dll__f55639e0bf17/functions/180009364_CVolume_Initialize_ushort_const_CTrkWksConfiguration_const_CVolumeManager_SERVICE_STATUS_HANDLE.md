# CVolume::Initialize(ushort const *,CTrkWksConfiguration const *,CVolumeManager *,SERVICE_STATUS_HANDLE__ *)

- ea: `0x180009364`
- end: `0x18000947f`
- name: `?Initialize@CVolume@@QEAAHPEBGPEBVCTrkWksConfiguration@@PEAVCVolumeManager@@PEAUSERVICE_STATUS_HANDLE__@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(CVolume *this, STRSAFE_PCNZWCH pszSrc, const struct CTrkWksConfiguration *, struct CVolumeManager *, struct SERVICE_STATUS_HANDLE__ *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x1800090c8`

## callees

- `0x1800073a0`
- `0x180009364`
- `0x180009640`
- `0x180009698`
- `0x1800099ec`
- `0x18000ed1c`
- `0x18000feb0`
- `0x180010fca`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009406`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009406`

## pseudocode

```c
__int64 __fastcall CVolume::Initialize(
        CVolume *this,
        STRSAFE_PCNZWCH pszSrc,
        const struct CTrkWksConfiguration *a3,
        struct CVolumeManager *a4,
        struct SERVICE_STATUS_HANDLE__ *a5)
{
  __int64 v9; // rsi
  size_t *v10; // r8
  unsigned int v11; // eax
  int v12; // eax
  size_t v14; // [rsp+20h] [rbp-48h]

  v9 = -1;
  *((_DWORD *)this + 12) = -1;
  memset_0((char *)this + 248, 0, 0x40u);
  StringCopyWorkerW((STRSAFE_LPWSTR)this + 30, 0x33u, v10, pszSrc, v14);
  do
    ++v9;
  while ( *((_WORD *)this + v9 + 30) );
  *((_WORD *)this + v9 + 29) = 0;
  *((_QWORD *)this + 4) = a3;
  *((_QWORD *)this + 5) = a4;
  *((_QWORD *)this + 360) = a5;
  *((_QWORD *)this + 359) = 0;
  v11 = *((_DWORD *)this + 4) & 0xFFFFFFE7;
  *((_DWORD *)this + 4) = v11;
  *((_DWORD *)this + 4) = v11 | 1;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  ++*((_DWORD *)this + 13);
  v12 = OpenVolume((const unsigned __int16 *)this + 30, (void **)this + 3);
  if ( v12 < 0 )
    TrkRaiseNtStatus(v12);
  CObjIdIndexChangeNotifier::Initialize((CVolume *)((char *)this + 576), (const unsigned __int16 *)this + 30, this);
  CVolume::Unlock(this);
  return 1;
}

```

## disassembly

```asm
0x180009364  mov     rax, rsp
0x180009367  mov     [rax+10h], rbx
0x18000936b  mov     [rax+18h], rsi
0x18000936f  mov     [rax+8], rcx
0x180009373  push    rdi
0x180009374  push    r12
0x180009376  push    r13
0x180009378  push    r14
0x18000937a  push    r15
0x18000937c  sub     rsp, 40h
0x180009380  mov     r15, r9
0x180009383  mov     r12, r8
0x180009386  mov     rbx, rdx
0x180009389  mov     rdi, rcx
0x18000938c  xor     r13d, r13d
0x18000938f  mov     [rax-38h], r13d
0x180009393  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009397  mov     [rcx+30h], esi
0x18000939a  add     rcx, 0F8h; void *
0x1800093a1  xor     edx, edx; Val
0x1800093a3  lea     r8d, [r13+40h]; Size
0x1800093a7  call    memset_0
0x1800093ac  lea     r14, [rdi+3Ch]
0x1800093b0  mov     r9, rbx; pszSrc
0x1800093b3  lea     edx, [rsi+34h]; cchDest
0x1800093b6  mov     rcx, r14; pszDest
0x1800093b9  call    StringCopyWorkerW
0x1800093be  inc     rsi
0x1800093c1  cmp     [r14+rsi*2], r13w
0x1800093c6  jnz     short loc_1800093BE
0x1800093c8  mov     [rdi+rsi*2+3Ah], r13w
0x1800093ce  mov     [rdi+20h], r12
0x1800093d2  mov     [rdi+28h], r15
0x1800093d6  mov     rax, [rsp+68h+arg_20]
0x1800093de  mov     [rdi+0B40h], rax
0x1800093e5  mov     [rdi+0B38h], r13
0x1800093ec  mov     eax, [rdi+10h]
0x1800093ef  and     eax, 0FFFFFFE7h
0x1800093f2  mov     [rdi+10h], eax
0x1800093f5  mov     ebx, 1
0x1800093fa  or      eax, ebx
0x1800093fc  mov     [rdi+10h], eax
0x1800093ff  lea     rcx, [rdi+0A8h]; lpCriticalSection
0x180009406  call    cs:__imp_EnterCriticalSection
0x18000940c  add     [rdi+34h], ebx
0x18000940f  lea     rdx, [rdi+18h]; void **
0x180009413  mov     rcx, r14; unsigned __int16 *
0x180009416  call    ?OpenVolume@@YAJPEBGPEAPEAX@Z; OpenVolume(ushort const *,void * *)
0x18000941b  test    eax, eax
0x18000941d  jns     short loc_180009426
0x18000941f  mov     ecx, eax; int
0x180009421  call    ?TrkRaiseNtStatus@@YAXJ@Z; TrkRaiseNtStatus(long)
0x180009426  lea     rcx, [rdi+240h]; this
0x18000942d  mov     r8, rdi; struct CVolume *
0x180009430  mov     rdx, r14; unsigned __int16 *
0x180009433  call    ?Initialize@CObjIdIndexChangeNotifier@@QEAAXPEBGPEAVCVolume@@@Z; CObjIdIndexChangeNotifier::Initialize(ushort const *,CVolume *)
0x180009438  mov     [rsp+68h+var_38], ebx
0x18000943c  mov     rcx, rdi; this
0x18000943f  call    ?Unlock@CVolume@@AEAAKXZ; CVolume::Unlock(void)
0x180009444  jmp     short loc_180009463
0x180009446  cmp     eax, 8DEAD021h
0x18000944b  jz      short loc_18000945F
0x18000944d  mov     r8d, eax; int
0x180009450  xor     r9d, r9d; unsigned __int16 *
0x180009453  lea     edx, [r9+71h]; unsigned int
0x180009457  lea     ecx, [rdx-1]; unsigned int
0x18000945a  call    ?TrkReportInternalError@@YAJKKJPEBG@Z; TrkReportInternalError(ulong,ulong,long,ushort const *)
0x18000945f  mov     ebx, [rsp+68h+var_38]
0x180009463  mov     eax, ebx
0x180009465  lea     r11, [rsp+68h+var_28]
0x18000946a  mov     rbx, [r11+38h]
0x18000946e  mov     rsi, [r11+40h]
0x180009472  mov     rsp, r11
0x180009475  pop     r15
0x180009477  pop     r14
0x180009479  pop     r13
0x18000947b  pop     r12
0x18000947d  pop     rdi
0x18000947e  retn
0x180011626  push    rbp
0x180011628  sub     rsp, 30h
0x18001162c  mov     rbp, rdx
0x18001162f  mov     rcx, [rbp+70h]; this
0x180011633  call    ?Unlock@CVolume@@AEAAKXZ; CVolume::Unlock(void)
0x180011638  nop
0x180011639  add     rsp, 30h
0x18001163d  pop     rbp
0x18001163e  retn
0x180011640  push    rbp
0x180011642  sub     rsp, 30h
0x180011646  mov     rbp, rdx
0x180011649  mov     eax, 1
0x18001164e  add     rsp, 30h
0x180011652  pop     rbp
0x180011653  retn
```
