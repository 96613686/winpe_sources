# CASFPrioritizationObject::Write(ulong,uchar *,ulong *)

- ea: `0x18001d7f0`
- end: `0x18001d9f5`
- name: `?Write@CASFPrioritizationObject@@UEAAJKPEAEPEAK@Z`
- size: `517`
- prototype: `__int64 __fastcall(CASFPrioritizationObject *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x18001d7f0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFPrioritizationObject::Write(
        struct IWMSCriticalSection **this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  int v8; // ebx
  struct IWMSCriticalSection *v9; // rax
  unsigned int v10; // eax
  unsigned __int16 v12; // r11
  unsigned __int8 *v13; // rsi
  int v14; // eax
  char *i; // r8
  unsigned int v16; // r10d
  unsigned int v17; // edx
  struct IWMSCriticalSection *v18; // rcx
  char v19[8]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v20; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int64 v21; // [rsp+40h] [rbp-38h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v19, this[4]);
  if ( !this[5] )
  {
    v8 = -1072887818;
LABEL_11:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v19);
    return (unsigned int)v8;
  }
  if ( a4 && (!a2 || a3) )
  {
    v9 = *this;
    v21 = 0;
    v8 = (*((__int64 (__fastcall **)(struct IWMSCriticalSection **, _QWORD, unsigned __int64 *))v9 + 7))(this, 0, &v21);
    if ( v8 >= 0 )
    {
      v10 = v21;
      if ( v21 < 0x100000000LL )
      {
        *a4 = v21;
        if ( a2 >= v10 )
        {
          v12 = 0;
          v13 = a3 + 26;
          *(_OWORD *)a3 = *((_OWORD *)this + 3);
          *((_QWORD *)a3 + 2) = this[8];
          for ( *((_WORD *)a3 + 12) = *((_WORD *)this + 108); (unsigned int)v12 < *((_DWORD *)this + 54); v13 += 4 )
          {
            v14 = 0;
            if ( (unsigned int)v12 < *((_DWORD *)this + 54) )
            {
              for ( i = (char *)(this + 11); i; i = (char *)*((_QWORD *)i + 13) )
              {
                v16 = *((_DWORD *)i + 2);
                if ( v12 >= v16 && v12 < v16 + 20 )
                {
                  v17 = v12 - v16;
                  if ( ((unsigned __int8)i[((unsigned __int64)v17 >> 3) + 20]
                      & (unsigned __int8)CTSparseBlock<unsigned long,CASFPrioritizationObject::PRIORITIZATION_REC,20,0>::s_bSingleBitMasks[v17 & 7]) != 0 )
                  {
                    v14 = *(_DWORD *)&i[4 * v17 + 24];
                    goto LABEL_23;
                  }
                  break;
                }
              }
              if ( (*((_BYTE *)this + 100) & 1) != 0 )
                v14 = *((_DWORD *)this + 26);
            }
LABEL_23:
            *(_DWORD *)v13 = v14;
            ++v12;
          }
          v18 = this[5];
          if ( v18 )
          {
            v20 = 0;
            v8 = (**(__int64 (__fastcall ***)(struct IWMSCriticalSection *, GUID *, __int64 *))v18)(
                   v18,
                   &IID_IASFReadWriteTracker,
                   &v20);
            if ( v8 >= 0 )
            {
              (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)v20 + 80LL))(
                v20,
                a3,
                (unsigned int)((_DWORD)v13 - (_DWORD)a3),
                (char *)this + 48);
              if ( v20 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            }
          }
        }
        else
        {
          v8 = -1072887855;
        }
      }
      else
      {
        v8 = -1072887821;
      }
    }
    goto LABEL_11;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v19);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001d7f0  mov     [rsp+arg_8], rbx
0x18001d7f5  push    rbp
0x18001d7f6  push    rsi
0x18001d7f7  push    rdi
0x18001d7f8  push    r14
0x18001d7fa  push    r15
0x18001d7fc  sub     rsp, 50h
0x18001d800  mov     rax, cs:__security_cookie
0x18001d807  xor     rax, rsp
0x18001d80a  mov     [rsp+78h+var_30], rax
0x18001d80f  mov     esi, edx
0x18001d811  mov     rdi, rcx
0x18001d814  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18001d818  mov     r14, r9
0x18001d81b  lea     rcx, [rsp+78h+var_48]; this
0x18001d820  mov     rbp, r8
0x18001d823  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18001d828  cmp     qword ptr [rdi+28h], 0
0x18001d82d  jnz     short loc_18001D836
0x18001d82f  mov     ebx, 0C00D07F6h
0x18001d834  jmp     short loc_18001D898
0x18001d836  test    r14, r14
0x18001d839  jz      loc_18001D9C5
0x18001d83f  test    esi, esi
0x18001d841  jz      short loc_18001D84C
0x18001d843  test    rbp, rbp
0x18001d846  jz      loc_18001D9C5
0x18001d84c  mov     rax, [rdi]
0x18001d84f  lea     r8, [rsp+78h+var_38]
0x18001d854  xor     edx, edx
0x18001d856  mov     [rsp+78h+var_38], 0
0x18001d85f  mov     rcx, rdi
0x18001d862  mov     rax, [rax+38h]
0x18001d866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d86b  mov     ebx, eax
0x18001d86d  test    eax, eax
0x18001d86f  js      short loc_18001D898
0x18001d871  mov     rax, [rsp+78h+var_38]
0x18001d876  mov     rcx, 100000000h
0x18001d880  cmp     rax, rcx
0x18001d883  jb      short loc_18001D88C
0x18001d885  mov     ebx, 0C00D07F3h
0x18001d88a  jmp     short loc_18001D898
0x18001d88c  mov     [r14], eax
0x18001d88f  cmp     esi, eax
0x18001d891  jnb     short loc_18001D8A9
0x18001d893  mov     ebx, 0C00D07D1h
0x18001d898  lea     rcx, [rsp+78h+var_48]; this
0x18001d89d  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001d8a2  mov     eax, ebx
0x18001d8a4  jmp     loc_18001D9D4
0x18001d8a9  movups  xmm0, xmmword ptr [rdi+30h]
0x18001d8ad  xor     r11d, r11d
0x18001d8b0  lea     rsi, [rbp+1Ah]
0x18001d8b4  movdqu  xmmword ptr [rbp+0], xmm0
0x18001d8b9  mov     rax, [rdi+40h]
0x18001d8bd  mov     [rbp+10h], rax
0x18001d8c1  movzx   eax, word ptr [rdi+0D8h]
0x18001d8c8  mov     [rbp+18h], ax
0x18001d8cc  cmp     [rdi+0D8h], r11d
0x18001d8d3  jbe     short loc_18001D952
0x18001d8d5  movzx   edx, r11w
0x18001d8d9  xor     eax, eax
0x18001d8db  cmp     edx, [rdi+0D8h]
0x18001d8e1  jnb     short loc_18001D934
0x18001d8e3  lea     r8, [rdi+58h]
0x18001d8e7  test    r8, r8
0x18001d8ea  jz      short loc_18001D92B
0x18001d8ec  mov     r10d, [r8+8]
0x18001d8f0  cmp     edx, r10d
0x18001d8f3  jb      short loc_18001D8FD
0x18001d8f5  lea     ecx, [r10+14h]
0x18001d8f9  cmp     edx, ecx
0x18001d8fb  jb      short loc_18001D903
0x18001d8fd  mov     r8, [r8+68h]
0x18001d901  jmp     short loc_18001D8E7
0x18001d903  sub     edx, r10d
0x18001d906  lea     r15, ?s_bSingleBitMasks@?$CTSparseBlock@KUPRIORITIZATION_REC@CASFPrioritizationObject@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,CASFPrioritizationObject::PRIORITIZATION_REC,20,0>::s_bSingleBitMasks
0x18001d90d  mov     ecx, edx
0x18001d90f  shr     rcx, 3
0x18001d913  mov     r10d, edx
0x18001d916  and     edx, 7
0x18001d919  mov     cl, [rcx+r8+14h]
0x18001d91e  test    [rdx+r15], cl
0x18001d922  jz      short loc_18001D92B
0x18001d924  mov     eax, [r8+r10*4+18h]
0x18001d929  jmp     short loc_18001D934
0x18001d92b  test    byte ptr [rdi+64h], 1
0x18001d92f  jz      short loc_18001D934
0x18001d931  mov     eax, [rdi+68h]
0x18001d934  mov     [rsi], ax
0x18001d937  inc     r11w
0x18001d93b  shr     eax, 10h
0x18001d93e  mov     [rsi+2], ax
0x18001d942  add     rsi, 4
0x18001d946  movzx   eax, r11w
0x18001d94a  cmp     eax, [rdi+0D8h]
0x18001d950  jb      short loc_18001D8D5
0x18001d952  mov     rcx, [rdi+28h]
0x18001d956  test    rcx, rcx
0x18001d959  jz      loc_18001D898
0x18001d95f  mov     [rsp+78h+var_40], 0
0x18001d968  lea     r8, [rsp+78h+var_40]
0x18001d96d  mov     rax, [rcx]
0x18001d970  lea     rdx, IID_IASFReadWriteTracker
0x18001d977  mov     rax, [rax]
0x18001d97a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d97f  mov     ebx, eax
0x18001d981  test    eax, eax
0x18001d983  js      loc_18001D898
0x18001d989  mov     rcx, [rsp+78h+var_40]
0x18001d98e  lea     r9, [rdi+30h]
0x18001d992  sub     esi, ebp
0x18001d994  mov     rdx, rbp
0x18001d997  mov     r8d, esi
0x18001d99a  mov     rax, [rcx]
0x18001d99d  mov     rax, [rax+50h]
0x18001d9a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9a6  mov     rcx, [rsp+78h+var_40]
0x18001d9ab  test    rcx, rcx
0x18001d9ae  jz      loc_18001D898
0x18001d9b4  mov     rax, [rcx]
0x18001d9b7  mov     rax, [rax+10h]
0x18001d9bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9c0  jmp     loc_18001D898
0x18001d9c5  lea     rcx, [rsp+78h+var_48]; this
0x18001d9ca  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001d9cf  mov     eax, 80070057h
0x18001d9d4  mov     rcx, [rsp+78h+var_30]
0x18001d9d9  xor     rcx, rsp; StackCookie
0x18001d9dc  call    __security_check_cookie
0x18001d9e1  mov     rbx, [rsp+78h+arg_8]
0x18001d9e9  add     rsp, 50h
0x18001d9ed  pop     r15
0x18001d9ef  pop     r14
0x18001d9f1  pop     rdi
0x18001d9f2  pop     rsi
0x18001d9f3  pop     rbp
0x18001d9f4  retn
```
