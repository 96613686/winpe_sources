# CASFStreamPropertiesObjectExv1::GetDataUnitExtensionSystemInfo(ushort,_GUID *,ushort *,uchar *,ulong *)

- ea: `0x1800155a0`
- end: `0x180015684`
- name: `?GetDataUnitExtensionSystemInfo@CASFStreamPropertiesObjectExv1@@UEAAJGPEAU_GUID@@PEAGPEAEPEAK@Z`
- size: `228`
- prototype: `__int64 __fastcall(CASFStreamPropertiesObjectExv1 *__hidden this, unsigned __int16, struct _GUID *, unsigned __int16 *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x180015184`
- `0x1800155a0`
- `0x18003f2a0`

## pseudocode

```c
__int64 __fastcall CASFStreamPropertiesObjectExv1::GetDataUnitExtensionSystemInfo(
        struct IWMSCriticalSection **this,
        unsigned __int16 a2,
        struct _GUID *a3,
        unsigned __int16 *a4,
        unsigned __int8 *a5,
        unsigned int *a6)
{
  unsigned int v6; // ebp
  unsigned int *v10; // rbx
  __int64 v11; // rax
  unsigned int v12; // ebx
  unsigned __int8 *v13; // rcx
  unsigned int v14; // r8d
  char v16; // [rsp+40h] [rbp+8h] BYREF

  v6 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v16, this[4]);
  if ( a3 )
  {
    if ( a4 )
    {
      v10 = a6;
      if ( a6 )
      {
        if ( v6 < *((_DWORD *)this + 94) )
        {
          v11 = CTPtrArray<CASFStreamPropertiesObjectExv1::_DATA_UNIT_EXTENSION,20>::operator[](this + 20, v6);
          if ( !v11 )
          {
            v12 = -2147467259;
LABEL_12:
            CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v16);
            return v12;
          }
          v13 = a5;
          *a3 = *(struct _GUID *)v11;
          *a4 = *(_WORD *)(v11 + 16);
          v14 = *v10;
          *v10 = *(_DWORD *)(v11 + 32);
          if ( v13 )
          {
            if ( v14 < *(_DWORD *)(v11 + 32) )
            {
              v12 = -1072887855;
              goto LABEL_12;
            }
            memcpy_0(v13, *(const void **)(v11 + 24), *(unsigned int *)(v11 + 32));
          }
          CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v16);
          return 0;
        }
      }
    }
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v16);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800155a0  mov     [rsp+arg_8], rbx
0x1800155a5  mov     [rsp+arg_10], rbp
0x1800155aa  push    rsi
0x1800155ab  push    rdi
0x1800155ac  push    r14
0x1800155ae  sub     rsp, 20h
0x1800155b2  movzx   ebp, dx
0x1800155b5  mov     rdi, rcx
0x1800155b8  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x1800155bc  mov     rsi, r9
0x1800155bf  lea     rcx, [rsp+38h+arg_0]; this
0x1800155c4  mov     r14, r8
0x1800155c7  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x1800155cc  test    r14, r14
0x1800155cf  jz      loc_180015662
0x1800155d5  test    rsi, rsi
0x1800155d8  jz      loc_180015662
0x1800155de  mov     rbx, [rsp+38h+arg_28]
0x1800155e3  test    rbx, rbx
0x1800155e6  jz      short loc_180015662
0x1800155e8  mov     edx, ebp
0x1800155ea  cmp     ebp, [rdi+178h]
0x1800155f0  jnb     short loc_180015662
0x1800155f2  lea     rcx, [rdi+0A0h]
0x1800155f9  call    ??A?$CTPtrArray@U_DATA_UNIT_EXTENSION@CASFStreamPropertiesObjectExv1@@$0BE@@@QEBAPEAU_DATA_UNIT_EXTENSION@CASFStreamPropertiesObjectExv1@@K@Z; CTPtrArray<CASFStreamPropertiesObjectExv1::_DATA_UNIT_EXTENSION,20>::operator[](ulong)
0x1800155fe  mov     rdx, rax
0x180015601  test    rax, rax
0x180015604  jnz     short loc_18001560D
0x180015606  mov     ebx, 80004005h
0x18001560b  jmp     short loc_180015654
0x18001560d  movups  xmm0, xmmword ptr [rax]
0x180015610  mov     rcx, [rsp+38h+arg_20]; void *
0x180015615  movdqu  xmmword ptr [r14], xmm0
0x18001561a  movzx   eax, word ptr [rax+10h]
0x18001561e  mov     [rsi], ax
0x180015621  mov     r8d, [rbx]
0x180015624  mov     eax, [rdx+20h]
0x180015627  mov     [rbx], eax
0x180015629  test    rcx, rcx
0x18001562c  jz      short loc_180015641
0x18001562e  cmp     r8d, [rdx+20h]
0x180015632  jb      short loc_18001564F
0x180015634  mov     r8d, [rdx+20h]; Size
0x180015638  mov     rdx, [rdx+18h]; Src
0x18001563c  call    memcpy_0
0x180015641  lea     rcx, [rsp+38h+arg_0]; this
0x180015646  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001564b  xor     eax, eax
0x18001564d  jmp     short loc_180015671
0x18001564f  mov     ebx, 0C00D07D1h
0x180015654  lea     rcx, [rsp+38h+arg_0]; this
0x180015659  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001565e  mov     eax, ebx
0x180015660  jmp     short loc_180015671
0x180015662  lea     rcx, [rsp+38h+arg_0]; this
0x180015667  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001566c  mov     eax, 80070057h
0x180015671  mov     rbx, [rsp+38h+arg_8]
0x180015676  mov     rbp, [rsp+38h+arg_10]
0x18001567b  add     rsp, 20h
0x18001567f  pop     r14
0x180015681  pop     rdi
0x180015682  pop     rsi
0x180015683  retn
```
