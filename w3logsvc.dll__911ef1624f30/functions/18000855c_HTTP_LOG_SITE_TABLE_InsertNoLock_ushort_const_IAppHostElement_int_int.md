# HTTP_LOG_SITE_TABLE::InsertNoLock(ushort const *,IAppHostElement *,int,int)

- ea: `0x18000855c`
- end: `0x18000869b`
- name: `?InsertNoLock@HTTP_LOG_SITE_TABLE@@AEAAJPEBGPEAUIAppHostElement@@HH@Z`
- size: `319`
- prototype: `__int64 __fastcall(HTTP_LOG_SITE_TABLE *this, const unsigned __int16 *, struct IAppHostElement *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180008230`
- `0x180008858`

## callees

- `0x180001008`
- `0x180007984`
- `0x18000855c`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800085d1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800085d1`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_SITE_TABLE::InsertNoLock(
        HTTP_LOG_SITE_TABLE *this,
        const unsigned __int16 *a2,
        struct IAppHostElement *a3,
        int a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // rax
  HTTP_LOG_SITE_ENTRY *v9; // rbx
  int v10; // esi
  unsigned int v11; // r8d
  unsigned __int16 **v12; // r9
  unsigned __int16 *v13; // rdx
  unsigned __int16 v14; // ax
  unsigned __int16 v15; // cx
  __int64 v16; // r8

  v8 = (struct _RTL_CRITICAL_SECTION *)operator new(0x90u);
  v9 = (HTTP_LOG_SITE_ENTRY *)v8;
  if ( v8 )
  {
    LODWORD(v8->SpinCount) = 1;
    v8->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&HTTP_LOG_SITE_ENTRY::`vftable';
    v8[2].DebugInfo = 0;
    *(_QWORD *)&v8[2].LockCount = 0;
    v8[2].SpinCount = 0;
    *(_QWORD *)&v8->LockCount = 0;
    LOWORD(v8->LockSemaphore) = 0;
    v8->OwningThread = 0;
    v8[2].LockSemaphore = &v8[2].OwningThread;
    v8[2].OwningThread = &v8[2].OwningThread;
    InitializeCriticalSectionAndSpinCount(v8 + 1, 0x1000u);
    v10 = HTTP_LOG_SITE_ENTRY::Initialize(v9, a2, a4, a3);
    if ( v10 < 0 )
    {
      (*(void (__fastcall **)(HTTP_LOG_SITE_ENTRY *))(*(_QWORD *)v9 + 8LL))(v9);
    }
    else
    {
      v11 = 0;
      v12 = (unsigned __int16 **)(((unsigned __int64)v9 + 8) & -(__int64)(v9 != 0));
      v13 = *v12;
      v14 = **v12;
      if ( *((_DWORD *)this + 264) )
      {
        while ( v14 )
        {
          ++v13;
          v11 = v14 + 101 * v11;
          v14 = *v13;
        }
      }
      else
      {
        while ( v14 )
        {
          v15 = v14;
          v14 = *++v13;
          v11 = (v15 & 0xFFDF) + 101 * v11;
        }
      }
      v16 = v11 % 0x83;
      *(_QWORD *)((((unsigned __int64)v9 + 8) & -(__int64)(v9 != 0)) + 8) = *((_QWORD *)this + v16 + 1);
      *((_QWORD *)this + v16 + 1) = v12;
      ++*((_DWORD *)this + 266);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000855c  push    rbx
0x18000855e  push    rbp
0x18000855f  push    rsi
0x180008560  push    rdi
0x180008561  push    r14
0x180008563  push    r15
0x180008565  sub     rsp, 38h
0x180008569  mov     rdi, rcx
0x18000856c  mov     esi, r9d
0x18000856f  mov     ecx, 90h; Size
0x180008574  mov     rbp, r8
0x180008577  mov     r14, rdx
0x18000857a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000857f  xor     r15d, r15d
0x180008582  mov     [rsp+68h+var_48], rax
0x180008587  mov     rbx, rax
0x18000858a  test    rax, rax
0x18000858d  jz      loc_180008687
0x180008593  mov     dword ptr [rbx+20h], 1
0x18000859a  lea     rax, ??_7HTTP_LOG_SITE_ENTRY@@6B@; const HTTP_LOG_SITE_ENTRY::`vftable'
0x1800085a1  mov     [rbx], rax
0x1800085a4  lea     rcx, [rbx+28h]; lpCriticalSection
0x1800085a8  lea     rax, [rbx+60h]
0x1800085ac  mov     [rbx+50h], r15
0x1800085b0  mov     [rbx+58h], r15
0x1800085b4  mov     edx, 1000h; dwSpinCount
0x1800085b9  mov     [rbx+70h], r15
0x1800085bd  mov     [rbx+8], r15
0x1800085c1  mov     [rbx+18h], r15w
0x1800085c6  mov     [rbx+10h], r15
0x1800085ca  mov     [rax+8], rax
0x1800085ce  mov     [rax], rax
0x1800085d1  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800085d7  test    rbx, rbx
0x1800085da  jz      loc_180008687
0x1800085e0  mov     r9, rbp; struct IAppHostElement *
0x1800085e3  mov     r8d, esi; int
0x1800085e6  mov     rdx, r14; unsigned __int16 *
0x1800085e9  mov     rcx, rbx; this
0x1800085ec  call    ?Initialize@HTTP_LOG_SITE_ENTRY@@QEAAJPEBGHPEAUIAppHostElement@@@Z; HTTP_LOG_SITE_ENTRY::Initialize(ushort const *,int,IAppHostElement *)
0x1800085f1  mov     esi, eax
0x1800085f3  test    eax, eax
0x1800085f5  js      short loc_180008676
0x1800085f7  lea     rcx, [rbx+8]
0x1800085fb  mov     r8d, r15d
0x1800085fe  neg     rbx
0x180008601  sbb     r9, r9
0x180008604  and     r9, rcx
0x180008607  mov     rdx, [r9]
0x18000860a  movzx   eax, word ptr [rdx]
0x18000860d  cmp     [rdi+420h], r15d
0x180008614  jz      short loc_180008647
0x180008616  jmp     short loc_180008629
0x180008618  movzx   eax, ax
0x18000861b  lea     rdx, [rdx+2]
0x18000861f  imul    r8d, 65h ; 'e'
0x180008623  add     r8d, eax
0x180008626  movzx   eax, word ptr [rdx]
0x180008629  test    ax, ax
0x18000862c  jnz     short loc_180008618
0x18000862e  jmp     short loc_18000864C
0x180008630  movzx   ecx, ax
0x180008633  lea     rdx, [rdx+2]
0x180008637  movzx   eax, word ptr [rdx]
0x18000863a  and     ecx, 0FFDFh
0x180008640  imul    r8d, 65h ; 'e'
0x180008644  add     r8d, ecx
0x180008647  test    ax, ax
0x18000864a  jnz     short loc_180008630
0x18000864c  mov     eax, 0FA232CF3h
0x180008651  mul     r8d
0x180008654  shr     edx, 7
0x180008657  imul    eax, edx, 83h
0x18000865d  sub     r8d, eax
0x180008660  mov     rax, [rdi+r8*8+8]
0x180008665  mov     [r9+8], rax
0x180008669  mov     [rdi+r8*8+8], r9
0x18000866e  inc     dword ptr [rdi+428h]
0x180008674  jmp     short loc_18000868C
0x180008676  mov     rax, [rbx]
0x180008679  mov     rcx, rbx
0x18000867c  mov     rax, [rax+8]
0x180008680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008685  jmp     short loc_18000868C
0x180008687  mov     esi, 8007000Eh
0x18000868c  mov     eax, esi
0x18000868e  add     rsp, 38h
0x180008692  pop     r15
0x180008694  pop     r14
0x180008696  pop     rdi
0x180008697  pop     rsi
0x180008698  pop     rbp
0x180008699  pop     rbx
0x18000869a  retn
```
