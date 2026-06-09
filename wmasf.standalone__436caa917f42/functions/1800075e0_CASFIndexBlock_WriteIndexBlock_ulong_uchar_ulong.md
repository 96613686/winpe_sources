# CASFIndexBlock::WriteIndexBlock(ulong,uchar *,ulong *)

- ea: `0x1800075e0`
- end: `0x18000772d`
- name: `?WriteIndexBlock@CASFIndexBlock@@UEAAJKPEAEPEAK@Z`
- size: `333`
- prototype: `int(CASFIndexBlock *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x1800075e0`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFIndexBlock::WriteIndexBlock(
        CASFIndexBlock *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned int v8; // ebx
  struct IWMSCriticalSection *v9; // rax
  unsigned int v10; // eax
  int (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // rcx
  _BYTE v13[8]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v14; // [rsp+38h] [rbp-30h] BYREF
  size_t Size; // [rsp+40h] [rbp-28h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v13, *((struct IWMSCriticalSection **)this + 17));
  if ( *((_QWORD *)this + 5) )
  {
    if ( (a3 || !a2) && a4 )
    {
      if ( *((_DWORD *)this + 9) )
      {
        v8 = -1072887798;
      }
      else
      {
        v9 = *(struct IWMSCriticalSection **)this;
        Size = 0;
        (*((void (__fastcall **)(CASFIndexBlock *, size_t *))v9 + 4))(this, &Size);
        v10 = Size;
        if ( Size < 0x100000000LL )
        {
          *a4 = Size;
          if ( a2 >= v10 )
          {
            memcpy_0(a3, *((const void **)this + 11), v10);
            v11 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
            if ( v11 )
            {
              v14 = 0;
              if ( (**v11)(v11, &IID_IASFReadWriteTracker, &v14) >= 0 )
              {
                (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, GUID *))(*(_QWORD *)v14 + 80LL))(
                  v14,
                  a3,
                  *a4,
                  &CLSID_ASFIndexBlock);
                if ( v14 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
              }
            }
            v8 = 0;
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
    }
    else
    {
      v8 = -2147024809;
    }
  }
  else
  {
    v8 = -1072887818;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v13);
  return v8;
}

```

## disassembly

```asm
0x1800075e0  mov     [rsp+arg_8], rbx
0x1800075e5  push    rbp
0x1800075e6  push    rsi
0x1800075e7  push    rdi
0x1800075e8  sub     rsp, 50h
0x1800075ec  mov     rax, cs:__security_cookie
0x1800075f3  xor     rax, rsp
0x1800075f6  mov     [rsp+68h+var_20], rax
0x1800075fb  mov     ebp, edx
0x1800075fd  mov     rbx, rcx
0x180007600  mov     rdx, [rcx+88h]; struct IWMSCriticalSection *
0x180007607  mov     rdi, r9
0x18000760a  lea     rcx, [rsp+68h+var_38]; this
0x18000760f  mov     rsi, r8
0x180007612  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180007617  cmp     qword ptr [rbx+28h], 0
0x18000761c  jnz     short loc_180007628
0x18000761e  mov     ebx, 0C00D07F6h
0x180007623  jmp     loc_180007707
0x180007628  test    rsi, rsi
0x18000762b  jnz     short loc_180007631
0x18000762d  test    ebp, ebp
0x18000762f  jnz     short loc_180007636
0x180007631  test    rdi, rdi
0x180007634  jnz     short loc_180007640
0x180007636  mov     ebx, 80070057h
0x18000763b  jmp     loc_180007707
0x180007640  cmp     dword ptr [rbx+24h], 0
0x180007644  jz      short loc_180007650
0x180007646  mov     ebx, 0C00D080Ah
0x18000764b  jmp     loc_180007707
0x180007650  mov     rax, [rbx]
0x180007653  lea     rdx, [rsp+68h+Size]
0x180007658  mov     rcx, rbx
0x18000765b  mov     [rsp+68h+Size], 0
0x180007664  mov     rax, [rax+20h]
0x180007668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000766d  mov     rax, [rsp+68h+Size]
0x180007672  mov     rcx, 100000000h
0x18000767c  cmp     rax, rcx
0x18000767f  jb      short loc_180007688
0x180007681  mov     ebx, 0C00D07F3h
0x180007686  jmp     short loc_180007707
0x180007688  mov     [rdi], eax
0x18000768a  cmp     ebp, eax
0x18000768c  jnb     short loc_180007695
0x18000768e  mov     ebx, 0C00D07D1h
0x180007693  jmp     short loc_180007707
0x180007695  mov     rdx, [rbx+58h]; Src
0x180007699  mov     rcx, rsi; void *
0x18000769c  mov     r8d, eax; Size
0x18000769f  call    memcpy_0
0x1800076a4  mov     rcx, [rbx+28h]
0x1800076a8  test    rcx, rcx
0x1800076ab  jz      short loc_180007705
0x1800076ad  mov     [rsp+68h+var_30], 0
0x1800076b6  lea     r8, [rsp+68h+var_30]
0x1800076bb  mov     rax, [rcx]
0x1800076be  lea     rdx, IID_IASFReadWriteTracker
0x1800076c5  mov     rax, [rax]
0x1800076c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076cd  test    eax, eax
0x1800076cf  js      short loc_180007705
0x1800076d1  mov     rcx, [rsp+68h+var_30]
0x1800076d6  lea     r9, CLSID_ASFIndexBlock
0x1800076dd  mov     r8d, [rdi]
0x1800076e0  mov     rdx, rsi
0x1800076e3  mov     rax, [rcx]
0x1800076e6  mov     rax, [rax+50h]
0x1800076ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076ef  mov     rcx, [rsp+68h+var_30]
0x1800076f4  test    rcx, rcx
0x1800076f7  jz      short loc_180007705
0x1800076f9  mov     rax, [rcx]
0x1800076fc  mov     rax, [rax+10h]
0x180007700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007705  xor     ebx, ebx
0x180007707  lea     rcx, [rsp+68h+var_38]; this
0x18000770c  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180007711  mov     eax, ebx
0x180007713  mov     rcx, [rsp+68h+var_20]
0x180007718  xor     rcx, rsp; StackCookie
0x18000771b  call    __security_check_cookie
0x180007720  mov     rbx, [rsp+68h+arg_8]
0x180007725  add     rsp, 50h
0x180007729  pop     rdi
0x18000772a  pop     rsi
0x18000772b  pop     rbp
0x18000772c  retn
```
