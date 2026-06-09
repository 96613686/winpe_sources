# __wmainCRTStartup

- ea: `0x140001140`
- end: `0x1400012e7`
- name: `__wmainCRTStartup`
- size: `423`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400012f0`

## callees

- `0x140001140`
- `0x14000156e`
- `0x140001620`
- `0x140001690`
- `0x1400017f7`
- `0x1400027b0`
- `0x140003920`

## import_xrefs

- `msvcrt!exit` at `0x140001293`
- `msvcrt!exit` at `0x140001293`
- `msvcrt!_exit` at `0x1400012c1`
- `msvcrt!_exit` at `0x1400012c1`
- `msvcrt!_cexit` at `0x1400012a2`
- `msvcrt!_cexit` at `0x1400012d1`
- `msvcrt!_cexit` at `0x1400012a2`
- `msvcrt!_cexit` at `0x1400012d1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140001179`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140001179`

## pseudocode

```c
__int64 _wmainCRTStartup()
{
  PVOID StackBase; // rbx
  int v1; // esi
  signed __int64 v2; // rax
  int v3; // eax
  __int64 *i; // rdi
  __int64 result; // rax

  StackBase = NtCurrentTeb()->NtTib.StackBase;
  v1 = 0;
  while ( 1 )
  {
    v2 = _InterlockedCompareExchange64(&_native_startup_lock, (signed __int64)StackBase, 0);
    if ( !v2 )
      break;
    if ( (PVOID)v2 == StackBase )
    {
      v1 = 1;
      break;
    }
    Sleep(0x3E8u);
  }
  if ( _native_startup_state == 1 )
  {
    amsg_exit_0(31);
LABEL_18:
    if ( _native_startup_state == 1 )
    {
      initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
      _native_startup_state = 2;
    }
    if ( !v1 )
      _InterlockedExchange64(&_native_startup_lock, 0);
    if ( _dyn_tls_init_callback && (unsigned int)IsNonwritableInCurrentImage(&_dyn_tls_init_callback) )
      _guard_dispatch_icall_fptr();
    result = wmain(dword_1400088A8, qword_1400088B0);
    dword_1400088A0 = result;
    if ( !dword_1400088C0 )
      exit(result);
    if ( !dword_1400088A4 )
    {
      _cexit();
      return (unsigned int)dword_1400088A0;
    }
    return result;
  }
  v3 = _native_startup_state;
  if ( _native_startup_state )
  {
    dword_1400088A4 = 1;
    goto LABEL_18;
  }
  _native_startup_state = 1;
  for ( i = &_xi_a; i < &_xi_z; ++i )
  {
    if ( v3 )
      return 255;
    if ( *i )
      v3 = _guard_dispatch_icall_fptr();
  }
  if ( !v3 )
    goto LABEL_18;
  return 255;
}

```

## disassembly

```asm
0x140001140  push    rbx
0x140001142  push    rsi
0x140001143  push    rdi
0x140001144  push    r15
0x140001146  sub     rsp, 38h
0x14000114a  mov     rax, gs:30h
0x140001153  mov     rbx, [rax+8]
0x140001157  xor     esi, esi
0x140001159  xor     eax, eax
0x14000115b  lock cmpxchg cs:__native_startup_lock, rbx
0x140001164  jz      short loc_140001181
0x140001166  cmp     rax, rbx
0x140001169  jnz     short loc_140001174
0x14000116b  mov     ebx, 1
0x140001170  mov     esi, ebx
0x140001172  jmp     short loc_140001186
0x140001174  mov     ecx, 3E8h; dwMilliseconds
0x140001179  call    cs:__imp_Sleep
0x14000117f  jmp     short loc_140001159
0x140001181  mov     ebx, 1
0x140001186  mov     eax, cs:__native_startup_state
0x14000118c  cmp     eax, ebx
0x14000118e  jnz     short loc_14000119C
0x140001190  mov     ecx, 1Fh
0x140001195  call    _amsg_exit_0
0x14000119a  jmp     short loc_140001201
0x14000119c  mov     eax, cs:__native_startup_state
0x1400011a2  test    eax, eax
0x1400011a4  jnz     short loc_1400011FB
0x1400011a6  mov     cs:__native_startup_state, ebx
0x1400011ac  lea     r15, __xi_z
0x1400011b3  lea     rdi, __xi_a
0x1400011ba  mov     [rsp+58h+var_30], rdi
0x1400011bf  mov     [rsp+58h+var_38], eax
0x1400011c3  cmp     rdi, r15
0x1400011c6  jnb     short loc_1400011ED
0x1400011c8  test    eax, eax
0x1400011ca  jnz     short loc_1400011F1
0x1400011cc  cmp     qword ptr [rdi], 0
0x1400011d0  jz      short loc_1400011E2
0x1400011d2  mov     rax, [rdi]
0x1400011d5  mov     rcx, cs:__guard_dispatch_icall_fptr
0x1400011dc  call    rcx ; _guard_dispatch_icall_nop
0x1400011de  mov     [rsp+58h+var_38], eax
0x1400011e2  add     rdi, 8
0x1400011e6  mov     [rsp+58h+var_30], rdi
0x1400011eb  jmp     short loc_1400011C3
0x1400011ed  test    eax, eax
0x1400011ef  jz      short loc_140001201
0x1400011f1  mov     eax, 0FFh
0x1400011f6  jmp     loc_1400012DD
0x1400011fb  mov     cs:dword_1400088A4, ebx
0x140001201  mov     eax, cs:__native_startup_state
0x140001207  cmp     eax, ebx
0x140001209  jnz     short loc_140001228
0x14000120b  lea     rdx, __xc_z; Last
0x140001212  lea     rcx, __xc_a; First
0x140001219  call    _initterm_0
0x14000121e  mov     cs:__native_startup_state, 2
0x140001228  test    esi, esi
0x14000122a  jnz     short loc_140001235
0x14000122c  xor     eax, eax
0x14000122e  xchg    rax, cs:__native_startup_lock
0x140001235  cmp     cs:__dyn_tls_init_callback, 0
0x14000123d  jz      short loc_140001269
0x14000123f  lea     rcx, __dyn_tls_init_callback
0x140001246  call    _IsNonwritableInCurrentImage
0x14000124b  test    eax, eax
0x14000124d  jz      short loc_140001269
0x14000124f  xor     r8d, r8d
0x140001252  lea     edx, [r8+2]
0x140001256  xor     ecx, ecx
0x140001258  mov     rax, cs:__dyn_tls_init_callback
0x14000125f  mov     r9, cs:__guard_dispatch_icall_fptr
0x140001266  call    r9 ; _guard_dispatch_icall_nop
0x140001269  mov     r8, cs:qword_1400088B8
0x140001270  mov     rdx, cs:qword_1400088B0; unsigned __int16 **
0x140001277  mov     ecx, cs:dword_1400088A8; int
0x14000127d  call    wmain
0x140001282  mov     cs:dword_1400088A0, eax
0x140001288  cmp     cs:dword_1400088C0, 0
0x14000128f  jnz     short loc_140001299
0x140001291  mov     ecx, eax; Code
0x140001293  call    cs:__imp_exit
0x140001299  cmp     cs:dword_1400088A4, 0
0x1400012a0  jnz     short loc_1400012AE
0x1400012a2  call    cs:__imp__cexit
0x1400012a8  mov     eax, cs:dword_1400088A0
0x1400012ae  jmp     short loc_1400012DD
0x1400012b0  mov     cs:dword_1400088A0, eax
0x1400012b6  cmp     cs:dword_1400088C0, 0
0x1400012bd  jnz     short loc_1400012C8
0x1400012bf  mov     ecx, eax; Code
0x1400012c1  call    cs:__imp__exit
0x1400012c8  cmp     cs:dword_1400088A4, 0
0x1400012cf  jnz     short loc_1400012DD
0x1400012d1  call    cs:__imp__cexit
0x1400012d7  mov     eax, cs:dword_1400088A0
0x1400012dd  add     rsp, 38h
0x1400012e1  pop     r15
0x1400012e3  pop     rdi
0x1400012e4  pop     rsi
0x1400012e5  pop     rbx
0x1400012e6  retn
0x140003990  push    rbp
0x140003992  sub     rsp, 20h
0x140003996  mov     rbp, rdx
0x140003999  mov     rdx, rcx
0x14000399c  mov     rcx, [rcx]
0x14000399f  mov     ecx, [rcx]
0x1400039a1  call    _XcptFilter_0
0x1400039a6  nop
0x1400039a7  add     rsp, 20h
0x1400039ab  pop     rbp
0x1400039ac  retn
```
