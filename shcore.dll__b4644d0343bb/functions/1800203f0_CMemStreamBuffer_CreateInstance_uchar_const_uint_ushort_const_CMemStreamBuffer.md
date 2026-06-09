# CMemStreamBuffer::CreateInstance(uchar const *,uint,ushort const *,CMemStreamBuffer * *)

- ea: `0x1800203f0`
- end: `0x180020643`
- name: `?CreateInstance@CMemStreamBuffer@@SAJPEBEIPEBGPEAPEAV1@@Z`
- size: `595`
- prototype: `__int64 __fastcall(const unsigned __int8 *Src, size_t Size, LPCWSTR psz, struct CMemStreamBuffer **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800369c4`

## callees

- `0x18000ddd4`
- `0x180019300`
- `0x1800203f0`
- `0x180036c3c`
- `0x18004d37c`
- `0x180066cfc`
- `0x180068d9c`
- `0x18009341c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800204e3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800204e3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180020456`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180020456`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020553`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002060c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002061b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020553`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002060c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002061b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020520`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020520`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800204c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800204c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020638`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020638`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800204d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800204d0`

## pseudocode

```c
__int64 __fastcall CMemStreamBuffer::CreateInstance(
        const unsigned __int8 *Src,
        size_t Size,
        LPCWSTR psz,
        struct CMemStreamBuffer **a4)
{
  size_t v4; // rsi
  int v6; // r14d
  char *v9; // rax
  char *v10; // rbx
  _BYTE *v11; // rax
  __int64 v13; // rcx
  int v14; // eax
  unsigned int v15; // r8d
  unsigned int v16; // ecx
  unsigned int v17; // eax
  unsigned int v18; // [rsp+20h] [rbp-38h]
  unsigned int v19; // [rsp+78h] [rbp+20h]

  v4 = (unsigned int)Size;
  v6 = 0;
  *a4 = 0;
  v9 = (char *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  *(_DWORD *)v9 = 1;
  *((_QWORD *)v9 + 1) = 0;
  *((_QWORD *)v9 + 2) = 0;
  *((_DWORD *)v9 + 7) = 0;
  *((_QWORD *)v9 + 4) = 0;
  *((_QWORD *)v9 + 5) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v9 + 48));
  *((_QWORD *)v10 + 11) = 0;
  if ( !Src || !(_DWORD)v4 )
    goto LABEL_3;
  EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 48));
  if ( *((_QWORD *)v10 + 11) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 48));
    v6 = -2147287035;
    goto LABEL_7;
  }
  if ( (unsigned int)v4 <= *((_DWORD *)v10 + 4) )
    goto LABEL_19;
  v14 = -1;
  v15 = v4;
  if ( (int)v4 + 4096 >= (unsigned int)v4 )
    v14 = v4 + 4096;
  v16 = v4;
  if ( (int)v4 + 4096 >= (unsigned int)v4 )
    v15 = v14;
  v19 = v15;
  if ( 2 * v4 <= 0xFFFFFFFF )
    v16 = 2 * v4;
  v17 = v15;
  if ( v16 > v15 )
    v17 = v16;
  v18 = v17;
  v6 = CMemStreamBuffer::GrowBuffer((CMemStreamBuffer *)v10, v17);
  if ( v6 >= 0 || v18 > v19 && (v6 = CMemStreamBuffer::GrowBuffer((CMemStreamBuffer *)v10, v19), v6 >= 0) )
  {
LABEL_19:
    memcpy_0(*((void **)v10 + 1), Src, v4);
    if ( (unsigned int)v4 > *((_DWORD *)v10 + 5) )
      *((_DWORD *)v10 + 5) = v4;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 48));
    v6 = 0;
LABEL_3:
    if ( psz )
      v6 = SHStrDupW(psz, (LPWSTR *)v10 + 5);
    if ( v6 >= 0 )
    {
      *((_DWORD *)v10 + 6) = 2;
      _InterlockedIncrement((volatile signed __int32 *)v10);
      *a4 = (struct CMemStreamBuffer *)v10;
    }
    goto LABEL_7;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 48));
LABEL_7:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10, 0xFFFFFFFF) == 1 )
  {
    if ( *((_QWORD *)v10 + 4) )
    {
      CMemStreamBuffer::WriteToReg((CMemStreamBuffer *)v10);
      RegCloseKey(*((HKEY *)v10 + 4));
    }
    v11 = (_BYTE *)*((_QWORD *)v10 + 1);
    if ( v11 && !*((_QWORD *)v10 + 11) )
    {
      if ( (v10[28] & 1) != 0 )
      {
        v13 = *((unsigned int *)v10 + 4);
        if ( *((_DWORD *)v10 + 4) )
        {
          do
          {
            *v11++ = 0;
            --v13;
          }
          while ( v13 );
        }
      }
      LocalFree(*((HLOCAL *)v10 + 1));
    }
    CoTaskMemFree(*((LPVOID *)v10 + 5));
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(v10 + 88);
    DeleteCriticalSection((LPCRITICAL_SECTION)(v10 + 48));
    operator delete(v10, (const struct std::nothrow_t *)0x60);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800203f0  mov     [rsp+arg_10], rbx
0x1800203f5  push    rbp
0x1800203f6  push    rsi
0x1800203f7  push    rdi
0x1800203f8  push    r14
0x1800203fa  push    r15
0x1800203fc  sub     rsp, 30h
0x180020400  mov     esi, edx
0x180020402  mov     rbp, rcx
0x180020405  xor     r14d, r14d
0x180020408  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002040f  mov     ecx, 60h ; '`'; unsigned __int64
0x180020414  mov     [r9], r14
0x180020417  mov     rdi, r9
0x18002041a  mov     r15, r8
0x18002041d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180020422  mov     rbx, rax
0x180020425  test    rax, rax
0x180020428  jz      loc_180020561
0x18002042e  mov     [rsp+58h+arg_0], r12
0x180020433  lea     rcx, [rax+30h]; lpCriticalSection
0x180020437  mov     [rsp+58h+arg_8], r13
0x18002043c  mov     dword ptr [rax], 1
0x180020442  mov     [rax+8], r14
0x180020446  mov     [rax+10h], r14
0x18002044a  mov     [rax+1Ch], r14d
0x18002044e  mov     [rax+20h], r14
0x180020452  mov     [rax+28h], r14
0x180020456  call    cs:__imp_InitializeCriticalSection
0x18002045c  mov     [rbx+58h], r14
0x180020460  test    rbp, rbp
0x180020463  jnz     loc_180020514
0x180020469  test    r15, r15
0x18002046c  jz      short loc_18002047D
0x18002046e  lea     rdx, [rbx+28h]; ppwsz
0x180020472  mov     rcx, r15; psz
0x180020475  call    SHStrDupW
0x18002047a  mov     r14d, eax
0x18002047d  test    r14d, r14d
0x180020480  js      short loc_18002048F
0x180020482  mov     dword ptr [rbx+18h], 2
0x180020489  lock inc dword ptr [rbx]
0x18002048c  mov     [rdi], rbx
0x18002048f  mov     ecx, 0FFFFFFFFh
0x180020494  lock xadd [rbx], ecx
0x180020498  cmp     ecx, 1
0x18002049b  jnz     short loc_1800204F6
0x18002049d  cmp     qword ptr [rbx+20h], 0
0x1800204a2  jnz     loc_18002062C
0x1800204a8  mov     rax, [rbx+8]
0x1800204ac  test    rax, rax
0x1800204af  jz      short loc_1800204CC
0x1800204b1  cmp     qword ptr [rbx+58h], 0
0x1800204b6  jnz     short loc_1800204CC
0x1800204b8  test    byte ptr [rbx+1Ch], 1
0x1800204bc  jnz     loc_180020577
0x1800204c2  mov     rcx, [rbx+8]; hMem
0x1800204c6  call    cs:__imp_LocalFree
0x1800204cc  mov     rcx, [rbx+28h]; pv
0x1800204d0  call    cs:__imp_CoTaskMemFree
0x1800204d6  lea     rcx, [rbx+58h]
0x1800204da  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x1800204df  lea     rcx, [rbx+30h]; lpCriticalSection
0x1800204e3  call    cs:__imp_DeleteCriticalSection
0x1800204e9  mov     edx, 60h ; '`'; struct std::nothrow_t *
0x1800204ee  mov     rcx, rbx; void *
0x1800204f1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800204f6  mov     r12, [rsp+58h+arg_0]
0x1800204fb  mov     eax, r14d
0x1800204fe  mov     r13, [rsp+58h+arg_8]
0x180020503  mov     rbx, [rsp+58h+arg_10]
0x180020508  add     rsp, 30h
0x18002050c  pop     r15
0x18002050e  pop     r14
0x180020510  pop     rdi
0x180020511  pop     rsi
0x180020512  pop     rbp
0x180020513  retn
0x180020514  test    esi, esi
0x180020516  jz      loc_180020469
0x18002051c  lea     rcx, [rbx+30h]; lpCriticalSection
0x180020520  call    cs:__imp_EnterCriticalSection
0x180020526  cmp     [rbx+58h], r14
0x18002052a  jnz     loc_180020617
0x180020530  cmp     esi, [rbx+10h]
0x180020533  ja      short loc_180020595
0x180020535  mov     rcx, [rbx+8]; void *
0x180020539  mov     rax, rsi
0x18002053c  mov     r8, rax; Size
0x18002053f  mov     rdx, rbp; Src
0x180020542  call    memcpy_0
0x180020547  cmp     esi, [rbx+14h]
0x18002054a  jbe     short loc_18002054F
0x18002054c  mov     [rbx+14h], esi
0x18002054f  lea     rcx, [rbx+30h]; lpCriticalSection
0x180020553  call    cs:__imp_LeaveCriticalSection
0x180020559  xor     r14d, r14d
0x18002055c  jmp     loc_180020469
0x180020561  mov     rbx, [rsp+58h+arg_10]
0x180020566  mov     eax, 8007000Eh
0x18002056b  add     rsp, 30h
0x18002056f  pop     r15
0x180020571  pop     r14
0x180020573  pop     rdi
0x180020574  pop     rsi
0x180020575  pop     rbp
0x180020576  retn
0x180020577  mov     ecx, [rbx+10h]
0x18002057a  test    rcx, rcx
0x18002057d  jz      loc_1800204C2
0x180020583  mov     byte ptr [rax], 0
0x180020586  lea     rax, [rax+1]
0x18002058a  sub     rcx, 1
0x18002058e  jnz     short loc_180020583
0x180020590  jmp     loc_1800204C2
0x180020595  lea     ecx, [rsi+1000h]
0x18002059b  mov     r9d, 0FFFFFFFFh
0x1800205a1  cmp     ecx, esi
0x1800205a3  mov     eax, r9d
0x1800205a6  mov     r8d, esi
0x1800205a9  mov     rdx, rsi
0x1800205ac  cmovnb  eax, ecx
0x1800205af  mov     ecx, esi
0x1800205b1  cmovnb  r8d, eax
0x1800205b5  add     rdx, rdx
0x1800205b8  cmp     rdx, r9
0x1800205bb  mov     [rsp+58h+arg_18], r8d
0x1800205c0  mov     eax, r9d
0x1800205c3  cmovbe  eax, edx
0x1800205c6  cmovbe  ecx, eax
0x1800205c9  mov     eax, r8d
0x1800205cc  cmp     ecx, r8d
0x1800205cf  cmova   eax, ecx
0x1800205d2  mov     rcx, rbx; this
0x1800205d5  mov     edx, eax; unsigned int
0x1800205d7  mov     [rsp+58h+var_38], eax
0x1800205db  call    ?GrowBuffer@CMemStreamBuffer@@QEAAJK@Z; CMemStreamBuffer::GrowBuffer(ulong)
0x1800205e0  mov     r14d, eax
0x1800205e3  test    eax, eax
0x1800205e5  jns     loc_180020535
0x1800205eb  mov     edx, [rsp+58h+arg_18]; unsigned int
0x1800205ef  cmp     [rsp+58h+var_38], edx
0x1800205f3  jbe     short loc_180020608
0x1800205f5  mov     rcx, rbx; this
0x1800205f8  call    ?GrowBuffer@CMemStreamBuffer@@QEAAJK@Z; CMemStreamBuffer::GrowBuffer(ulong)
0x1800205fd  mov     r14d, eax
0x180020600  test    eax, eax
0x180020602  jns     loc_180020535
0x180020608  lea     rcx, [rbx+30h]; lpCriticalSection
0x18002060c  call    cs:__imp_LeaveCriticalSection
0x180020612  jmp     loc_18002048F
0x180020617  lea     rcx, [rbx+30h]; lpCriticalSection
0x18002061b  call    cs:__imp_LeaveCriticalSection
0x180020621  mov     r14d, 80030005h
0x180020627  jmp     loc_18002048F
0x18002062c  mov     rcx, rbx; this
0x18002062f  call    ?WriteToReg@CMemStreamBuffer@@AEAAHXZ; CMemStreamBuffer::WriteToReg(void)
0x180020634  mov     rcx, [rbx+20h]; hKey
0x180020638  call    cs:__imp_RegCloseKey
0x18002063e  jmp     loc_1800204A8
```
