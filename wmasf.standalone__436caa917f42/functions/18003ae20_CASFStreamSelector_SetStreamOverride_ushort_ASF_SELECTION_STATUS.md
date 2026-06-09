# CASFStreamSelector::SetStreamOverride(ushort,_ASF_SELECTION_STATUS)

- ea: `0x18003ae20`
- end: `0x18003aea7`
- name: `?SetStreamOverride@CASFStreamSelector@@UEAAJGW4_ASF_SELECTION_STATUS@@@Z`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x180033a40`
- `0x180037f08`
- `0x180039510`
- `0x18003ae20`

## pseudocode

```c
__int64 __fastcall CASFStreamSelector::SetStreamOverride(__int64 a1, unsigned __int16 a2, int a3)
{
  __int64 v6; // rcx
  int v7; // ebx
  unsigned int v9; // [rsp+40h] [rbp+8h] BYREF
  char v10; // [rsp+58h] [rbp+20h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v10, *(struct IWMSCriticalSection **)(a1 + 16));
  if ( *(_DWORD *)(a1 + 48) || (v7 = CASFStreamSelector::ParseHeader((CASFStreamSelector *)a1), v7 >= 0) )
  {
    v9 = 0;
    if ( (int)CASFStreamSelector::GetStreamInfo(v6, a1 + 64, a2, &v9) >= 0 )
    {
      v7 = 0;
      *(_DWORD *)(CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](a1 + 64, v9) + 20) = a3;
    }
    else
    {
      v7 = -2147024809;
    }
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v10);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003ae20  mov     [rsp+arg_8], rbx
0x18003ae25  push    rbp
0x18003ae26  push    rsi
0x18003ae27  push    rdi
0x18003ae28  sub     rsp, 20h
0x18003ae2c  movzx   ebp, dx
0x18003ae2f  mov     rdi, rcx
0x18003ae32  mov     rdx, [rcx+10h]; struct IWMSCriticalSection *
0x18003ae36  mov     esi, r8d
0x18003ae39  lea     rcx, [rsp+38h+arg_18]; this
0x18003ae3e  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18003ae43  cmp     dword ptr [rdi+30h], 0
0x18003ae47  jnz     short loc_18003AE57
0x18003ae49  mov     rcx, rdi; this
0x18003ae4c  call    ?ParseHeader@CASFStreamSelector@@IEAAJXZ; CASFStreamSelector::ParseHeader(void)
0x18003ae51  mov     ebx, eax
0x18003ae53  test    eax, eax
0x18003ae55  js      short loc_18003AE8E
0x18003ae57  lea     r9, [rsp+38h+arg_0]
0x18003ae5c  mov     [rsp+38h+arg_0], 0
0x18003ae64  movzx   r8d, bp
0x18003ae68  lea     rdx, [rdi+40h]
0x18003ae6c  call    ?GetStreamInfo@CASFStreamSelector@@IEAAJPEAV?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@GPEAK@Z; CASFStreamSelector::GetStreamInfo(CTDynArray<CASFStreamSelector::STREAM_INFO *,20> *,ushort,ulong *)
0x18003ae71  test    eax, eax
0x18003ae73  jns     short loc_18003AE7C
0x18003ae75  mov     ebx, 80070057h
0x18003ae7a  jmp     short loc_18003AE8E
0x18003ae7c  mov     edx, [rsp+38h+arg_0]
0x18003ae80  lea     rcx, [rdi+40h]
0x18003ae84  call    ??A?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@QEBAPEAUSTREAM_INFO@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](ulong)
0x18003ae89  xor     ebx, ebx
0x18003ae8b  mov     [rax+14h], esi
0x18003ae8e  lea     rcx, [rsp+38h+arg_18]; this
0x18003ae93  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18003ae98  mov     eax, ebx
0x18003ae9a  mov     rbx, [rsp+38h+arg_8]
0x18003ae9f  add     rsp, 20h
0x18003aea3  pop     rdi
0x18003aea4  pop     rsi
0x18003aea5  pop     rbp
0x18003aea6  retn
```
