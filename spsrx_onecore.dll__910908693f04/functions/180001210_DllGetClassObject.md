# DllGetClassObject

- ea: `0x180001210`
- end: `0x180001305`
- name: `DllGetClassObject`
- size: `245`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001210`
- `0x180001330`
- `0x180006418`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000128d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000128d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800012ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800012ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const struct _GUID *v5; // rbp
  HRESULT v7; // edi
  __int64 v8; // rbx

  v5 = rclsid;
  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v7 = 0;
  v8 = qword_1800152F8;
  if ( qword_1800152F8 && *(_QWORD *)qword_1800152F8 )
  {
    while ( !*(_QWORD *)(v8 + 16) || !(unsigned int)InlineIsEqualGUID(v5, *(_QWORD *)v8) )
    {
      v8 += 72;
      if ( !*(_QWORD *)v8 )
        goto LABEL_15;
    }
    if ( !*(_QWORD *)(v8 + 32) )
    {
      EnterCriticalSection(&CriticalSection);
      if ( !*(_QWORD *)(v8 + 32) )
        v7 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v8 + 16))(
               *(_QWORD *)(v8 + 24),
               &GUID_00000000_0000_0000_c000_000000000046,
               v8 + 32);
      LeaveCriticalSection(&CriticalSection);
    }
    rclsid = *(const IID *const *)(v8 + 32);
    if ( rclsid )
      v7 = (**(__int64 (__fastcall ***)(const IID *const, const IID *const, LPVOID *))&rclsid->Data1)(rclsid, riid, ppv);
  }
LABEL_15:
  if ( !*ppv && !v7 )
    return ATL::AtlComModuleGetClassObject((struct ATL::_ATL_COM_MODULE70 *)rclsid, v5, riid, ppv);
  return v7;
}

```

## disassembly

```asm
0x180001210  push    rbx
0x180001212  push    rbp
0x180001213  push    rsi
0x180001214  push    rdi
0x180001215  push    r14
0x180001217  push    r15
0x180001219  sub     rsp, 28h
0x18000121d  mov     rsi, r8
0x180001220  mov     r15, rdx
0x180001223  mov     rbp, rcx
0x180001226  test    r8, r8
0x180001229  jnz     short loc_18000123D
0x18000122b  mov     eax, 80004003h
0x180001230  add     rsp, 28h
0x180001234  pop     r15
0x180001236  pop     r14
0x180001238  pop     rdi
0x180001239  pop     rsi
0x18000123a  pop     rbp
0x18000123b  pop     rbx
0x18000123c  retn
0x18000123d  mov     qword ptr [r8], 0
0x180001244  xor     edi, edi
0x180001246  mov     rbx, cs:qword_1800152F8
0x18000124d  test    rbx, rbx
0x180001250  jz      loc_1800012DC
0x180001256  cmp     [rbx], rdi
0x180001259  jz      loc_1800012DC
0x18000125f  nop
0x180001260  cmp     [rbx+10h], rdi
0x180001264  jz      short loc_180001275
0x180001266  mov     rdx, [rbx]
0x180001269  mov     rcx, rbp
0x18000126c  call    InlineIsEqualGUID
0x180001271  test    eax, eax
0x180001273  jnz     short loc_180001280
0x180001275  add     rbx, 48h ; 'H'
0x180001279  cmp     [rbx], rdi
0x18000127c  jnz     short loc_180001260
0x18000127e  jmp     short loc_1800012DC
0x180001280  cmp     [rbx+20h], rdi
0x180001284  jnz     short loc_1800012C0
0x180001286  lea     rcx, CriticalSection; lpCriticalSection
0x18000128d  call    cs:__imp_EnterCriticalSection
0x180001293  cmp     [rbx+20h], rdi
0x180001297  jnz     short loc_1800012B3
0x180001299  lea     r8, [rbx+20h]
0x18000129d  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800012a4  mov     rcx, [rbx+18h]
0x1800012a8  mov     rax, [rbx+10h]
0x1800012ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012b1  mov     edi, eax
0x1800012b3  lea     rcx, CriticalSection; lpCriticalSection
0x1800012ba  call    cs:__imp_LeaveCriticalSection
0x1800012c0  mov     rcx, [rbx+20h]
0x1800012c4  test    rcx, rcx
0x1800012c7  jz      short loc_1800012DC
0x1800012c9  mov     rax, [rcx]
0x1800012cc  mov     r8, rsi
0x1800012cf  mov     rdx, r15
0x1800012d2  mov     rax, [rax]
0x1800012d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012da  mov     edi, eax
0x1800012dc  cmp     qword ptr [rsi], 0
0x1800012e0  jnz     short loc_1800012F6
0x1800012e2  test    edi, edi
0x1800012e4  jnz     short loc_1800012F6
0x1800012e6  mov     r9, rsi; void **
0x1800012e9  mov     r8, r15; struct _GUID *
0x1800012ec  mov     rdx, rbp; struct _GUID *
0x1800012ef  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x1800012f4  mov     edi, eax
0x1800012f6  mov     eax, edi
0x1800012f8  add     rsp, 28h
0x1800012fc  pop     r15
0x1800012fe  pop     r14
0x180001300  pop     rdi
0x180001301  pop     rsi
0x180001302  pop     rbp
0x180001303  pop     rbx
0x180001304  retn
```
