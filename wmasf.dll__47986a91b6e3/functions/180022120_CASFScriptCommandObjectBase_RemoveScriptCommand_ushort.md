# CASFScriptCommandObjectBase::RemoveScriptCommand(ushort)

- ea: `0x180022120`
- end: `0x1800221c8`
- name: `?RemoveScriptCommand@CASFScriptCommandObjectBase@@UEAAJG@Z`
- size: `168`
- prototype: `__int64 __fastcall(CASFScriptCommandObjectBase *__hidden this, unsigned __int16)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800011c0`
- `0x1800021dc`
- `0x18000220c`
- `0x180021af4`
- `0x180022120`
- `0x1800221d0`

## pseudocode

```c
__int64 __fastcall CASFScriptCommandObjectBase::RemoveScriptCommand(
        struct IWMSCriticalSection **this,
        unsigned __int16 a2)
{
  unsigned int v2; // edi
  unsigned int v4; // ebx
  unsigned int v5; // esi
  char *v6; // rdi
  __int64 v7; // rax
  int v8; // ebx
  _BYTE v10[40]; // [rsp+20h] [rbp-28h] BYREF
  char v11; // [rsp+50h] [rbp+8h] BYREF

  v2 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v11, this[4]);
  if ( this[5] )
  {
    v5 = v2;
    if ( v2 < *((_DWORD *)this + 214) )
    {
      v6 = (char *)(this + 38);
      v7 = CTDynArray<CASFScriptCommandObjectBase::COMMAND_RECORD,20>::operator[](this + 38, v10, v5);
      operator delete(*(void **)(v7 + 16));
      if ( v5 + 1 <= *((_DWORD *)this + 214) )
      {
        v8 = 0;
        do
        {
          if ( (int)CTSparseBlock<unsigned long,CASFScriptCommandObjectBase::COMMAND_RECORD,20,0>::RemoveValue(v6, v5) < 0 )
            break;
          --*((_DWORD *)v6 + 138);
          ++v8;
        }
        while ( !v8 );
      }
      v4 = 0;
    }
    else
    {
      v4 = -1072887824;
    }
  }
  else
  {
    v4 = -1072887818;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v11);
  return v4;
}

```

## disassembly

```asm
0x180022120  mov     [rsp+arg_8], rbx
0x180022125  mov     [rsp+arg_10], rsi
0x18002212a  push    rdi
0x18002212b  sub     rsp, 40h
0x18002212f  movzx   edi, dx
0x180022132  mov     rbx, rcx
0x180022135  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180022139  lea     rcx, [rsp+48h+arg_0]; this
0x18002213e  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180022143  cmp     qword ptr [rbx+28h], 0
0x180022148  jnz     short loc_180022151
0x18002214a  mov     ebx, 0C00D07F6h
0x18002214f  jmp     short loc_1800221AC
0x180022151  mov     esi, edi
0x180022153  cmp     edi, [rbx+358h]
0x180022159  jb      short loc_180022162
0x18002215b  mov     ebx, 0C00D07F0h
0x180022160  jmp     short loc_1800221AC
0x180022162  lea     rdi, [rbx+130h]
0x180022169  mov     r8d, esi
0x18002216c  mov     rcx, rdi
0x18002216f  lea     rdx, [rsp+48h+var_28]
0x180022174  call    ??A?$CTDynArray@UCOMMAND_RECORD@CASFScriptCommandObjectBase@@$0BE@@@QEBA?AUCOMMAND_RECORD@CASFScriptCommandObjectBase@@K@Z; CTDynArray<CASFScriptCommandObjectBase::COMMAND_RECORD,20>::operator[](ulong)
0x180022179  mov     rcx, [rax+10h]; Block
0x18002217d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022182  lea     eax, [rsi+1]
0x180022185  cmp     eax, [rdi+228h]
0x18002218b  ja      short loc_1800221AA
0x18002218d  xor     ebx, ebx
0x18002218f  mov     edx, esi
0x180022191  mov     rcx, rdi
0x180022194  call    ?RemoveValue@?$CTSparseBlock@KUCOMMAND_RECORD@CASFScriptCommandObjectBase@@$0BE@$0A@@@QEAAJK@Z; CTSparseBlock<ulong,CASFScriptCommandObjectBase::COMMAND_RECORD,20,0>::RemoveValue(ulong)
0x180022199  test    eax, eax
0x18002219b  js      short loc_1800221AA
0x18002219d  dec     dword ptr [rdi+228h]
0x1800221a3  inc     ebx
0x1800221a5  cmp     ebx, 1
0x1800221a8  jb      short loc_18002218F
0x1800221aa  xor     ebx, ebx
0x1800221ac  lea     rcx, [rsp+48h+arg_0]; this
0x1800221b1  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800221b6  mov     rsi, [rsp+48h+arg_10]
0x1800221bb  mov     eax, ebx
0x1800221bd  mov     rbx, [rsp+48h+arg_8]
0x1800221c2  add     rsp, 40h
0x1800221c6  pop     rdi
0x1800221c7  retn
```
