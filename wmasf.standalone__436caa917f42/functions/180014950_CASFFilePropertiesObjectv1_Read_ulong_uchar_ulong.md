# CASFFilePropertiesObjectv1::Read(ulong,uchar *,ulong *)

- ea: `0x180014950`
- end: `0x180014b18`
- name: `?Read@CASFFilePropertiesObjectv1@@UEAAJKPEAEPEAK@Z`
- size: `456`
- prototype: `__int64 __fastcall(struct IWMSCriticalSection **this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180014950`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFFilePropertiesObjectv1::Read(
        struct IWMSCriticalSection **this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned int v8; // ebx
  unsigned __int64 v9; // rax
  int v10; // eax
  struct IWMSCriticalSection *v11; // rcx
  char v13[8]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v14; // [rsp+38h] [rbp-30h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v13, this[4]);
  if ( !this[5] )
  {
    v8 = -1072887818;
LABEL_17:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v13);
    return v8;
  }
  if ( !a4 )
    goto LABEL_18;
  if ( !a2 )
  {
LABEL_16:
    *a4 = 104;
    v8 = -1072887855;
    goto LABEL_17;
  }
  if ( !a3 )
  {
LABEL_18:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v13);
    return 2147942487LL;
  }
  if ( a2 < 0x68 )
    goto LABEL_16;
  *((_OWORD *)this + 3) = *(_OWORD *)a3;
  this[8] = (struct IWMSCriticalSection *)*((_QWORD *)a3 + 2);
  *((_OWORD *)this + 5) = *(_OWORD *)(a3 + 24);
  this[24] = (struct IWMSCriticalSection *)*((_QWORD *)a3 + 5);
  this[12] = (struct IWMSCriticalSection *)*((_QWORD *)a3 + 6);
  v9 = *((_QWORD *)a3 + 7);
  if ( v9 > 0xFFFFFFFF )
  {
    v8 = -1072887838;
    goto LABEL_17;
  }
  *((_DWORD *)this + 39) = v9;
  this[15] = (struct IWMSCriticalSection *)*((_QWORD *)a3 + 8);
  this[14] = (struct IWMSCriticalSection *)*((_QWORD *)a3 + 9);
  this[25] = (struct IWMSCriticalSection *)*((_QWORD *)a3 + 10);
  *((_DWORD *)this + 34) = 0;
  v10 = *((_DWORD *)a3 + 22);
  *((_DWORD *)this + 52) = v10;
  if ( (v10 & 1) != 0 )
    *((_DWORD *)this + 34) = 1;
  *((_DWORD *)this + 37) = *((_DWORD *)a3 + 23);
  *((_DWORD *)this + 38) = *((_DWORD *)a3 + 24);
  *((_DWORD *)this + 36) = *((_DWORD *)a3 + 25);
  *a4 = 104;
  v11 = this[5];
  if ( v11 )
  {
    v14 = 0;
    if ( (**(int (__fastcall ***)(struct IWMSCriticalSection *, GUID *, __int64 *))v11)(
           v11,
           &IID_IASFReadWriteTracker,
           &v14) >= 0 )
    {
      (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)v14 + 72LL))(
        v14,
        a3,
        *a4,
        (char *)this + 48);
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
  *((GUID *)this + 3) = CLSID_ASFFilePropertiesObject;
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v13);
  return 0;
}

```

## disassembly

```asm
0x180014950  mov     [rsp+arg_8], rbx
0x180014955  push    rbp
0x180014956  push    rsi
0x180014957  push    rdi
0x180014958  sub     rsp, 50h
0x18001495c  mov     rax, cs:__security_cookie
0x180014963  xor     rax, rsp
0x180014966  mov     [rsp+68h+var_28], rax
0x18001496b  mov     ebp, edx
0x18001496d  mov     rbx, rcx
0x180014970  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180014974  mov     rsi, r9
0x180014977  lea     rcx, [rsp+68h+var_38]; this
0x18001497c  mov     rdi, r8
0x18001497f  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180014984  cmp     qword ptr [rbx+28h], 0
0x180014989  jnz     short loc_180014995
0x18001498b  mov     ebx, 0C00D07F6h
0x180014990  jmp     loc_180014AE1
0x180014995  test    rsi, rsi
0x180014998  jz      loc_180014AEF
0x18001499e  mov     edx, 68h ; 'h'
0x1800149a3  test    ebp, ebp
0x1800149a5  jz      loc_180014ADA
0x1800149ab  test    rdi, rdi
0x1800149ae  jz      loc_180014AEF
0x1800149b4  cmp     ebp, edx
0x1800149b6  jb      loc_180014ADA
0x1800149bc  movups  xmm0, xmmword ptr [rdi]
0x1800149bf  lea     rbp, [rbx+30h]
0x1800149c3  mov     ecx, 0FFFFFFFFh
0x1800149c8  movdqu  xmmword ptr [rbp+0], xmm0
0x1800149cd  mov     rax, [rdi+10h]
0x1800149d1  mov     [rbx+40h], rax
0x1800149d5  movups  xmm0, xmmword ptr [rdi+18h]
0x1800149d9  movdqu  xmmword ptr [rbx+50h], xmm0
0x1800149de  mov     rax, [rdi+28h]
0x1800149e2  mov     [rbx+0C0h], rax
0x1800149e9  mov     rax, [rdi+30h]
0x1800149ed  mov     [rbx+60h], rax
0x1800149f1  mov     rax, [rdi+38h]
0x1800149f5  cmp     rax, rcx
0x1800149f8  jbe     short loc_180014A04
0x1800149fa  mov     ebx, 0C00D07E2h
0x1800149ff  jmp     loc_180014AE1
0x180014a04  mov     [rbx+9Ch], eax
0x180014a0a  mov     rax, [rdi+40h]
0x180014a0e  mov     [rbx+78h], rax
0x180014a12  mov     rax, [rdi+48h]
0x180014a16  mov     [rbx+70h], rax
0x180014a1a  mov     rax, [rdi+50h]
0x180014a1e  mov     [rbx+0C8h], rax
0x180014a25  mov     dword ptr [rbx+88h], 0
0x180014a2f  mov     eax, [rdi+58h]
0x180014a32  mov     [rbx+0D0h], eax
0x180014a38  test    al, 1
0x180014a3a  jz      short loc_180014A46
0x180014a3c  mov     dword ptr [rbx+88h], 1
0x180014a46  mov     eax, [rdi+5Ch]
0x180014a49  mov     [rbx+94h], eax
0x180014a4f  mov     eax, [rdi+60h]
0x180014a52  mov     [rbx+98h], eax
0x180014a58  mov     eax, [rdi+64h]
0x180014a5b  mov     [rbx+90h], eax
0x180014a61  mov     [rsi], edx
0x180014a63  mov     rcx, [rbx+28h]
0x180014a67  test    rcx, rcx
0x180014a6a  jz      short loc_180014AC0
0x180014a6c  mov     [rsp+68h+var_30], 0
0x180014a75  lea     r8, [rsp+68h+var_30]
0x180014a7a  mov     rax, [rcx]
0x180014a7d  lea     rdx, IID_IASFReadWriteTracker
0x180014a84  mov     rax, [rax]
0x180014a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a8c  test    eax, eax
0x180014a8e  js      short loc_180014AC0
0x180014a90  mov     rcx, [rsp+68h+var_30]
0x180014a95  mov     r9, rbp
0x180014a98  mov     r8d, [rsi]
0x180014a9b  mov     rdx, rdi
0x180014a9e  mov     rax, [rcx]
0x180014aa1  mov     rax, [rax+48h]
0x180014aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014aaa  mov     rcx, [rsp+68h+var_30]
0x180014aaf  test    rcx, rcx
0x180014ab2  jz      short loc_180014AC0
0x180014ab4  mov     rax, [rcx]
0x180014ab7  mov     rax, [rax+10h]
0x180014abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ac0  movups  xmm0, xmmword ptr cs:CLSID_ASFFilePropertiesObject.Data1
0x180014ac7  lea     rcx, [rsp+68h+var_38]; this
0x180014acc  movdqu  xmmword ptr [rbp+0], xmm0
0x180014ad1  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180014ad6  xor     eax, eax
0x180014ad8  jmp     short loc_180014AFE
0x180014ada  mov     [rsi], edx
0x180014adc  mov     ebx, 0C00D07D1h
0x180014ae1  lea     rcx, [rsp+68h+var_38]; this
0x180014ae6  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180014aeb  mov     eax, ebx
0x180014aed  jmp     short loc_180014AFE
0x180014aef  lea     rcx, [rsp+68h+var_38]; this
0x180014af4  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180014af9  mov     eax, 80070057h
0x180014afe  mov     rcx, [rsp+68h+var_28]
0x180014b03  xor     rcx, rsp; StackCookie
0x180014b06  call    __security_check_cookie
0x180014b0b  mov     rbx, [rsp+68h+arg_8]
0x180014b10  add     rsp, 50h
0x180014b14  pop     rdi
0x180014b15  pop     rsi
0x180014b16  pop     rbp
0x180014b17  retn
```
