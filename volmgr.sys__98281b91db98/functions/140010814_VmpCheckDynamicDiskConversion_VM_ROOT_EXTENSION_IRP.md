# VmpCheckDynamicDiskConversion(VM_ROOT_EXTENSION *,_IRP *)

- ea: `0x140010814`
- end: `0x140010892`
- name: `?VmpCheckDynamicDiskConversion@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z`
- size: `126`
- prototype: `__int64 __fastcall(struct VM_ROOT_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001ae0`

## callees

- `0x1400029e0`
- `0x140002a30`
- `0x140010814`

## pseudocode

```c
__int64 __fastcall VmpCheckDynamicDiskConversion(struct VM_ROOT_EXTENSION *a1, struct _IRP *a2)
{
  struct _IRP *MasterIrp; // rsi
  unsigned int v5; // edi
  __int64 *i; // rcx

  if ( a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.Options < 0x58 )
    return 3221225485LL;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  v5 = 0;
  VmpAcquireAll(a1);
  for ( i = (__int64 *)*((_QWORD *)a1 + 26); i != (__int64 *)((char *)a1 + 208); i = (__int64 *)*i )
  {
    if ( !*((_BYTE *)i + 394) && *((_DWORD *)i + 88) == *(_DWORD *)&MasterIrp->Type && *((_BYTE *)i + 112) )
    {
      v5 = -1073741637;
      break;
    }
  }
  VmpReleaseAll(a1);
  return v5;
}

```

## disassembly

```asm
0x140010814  mov     [rsp+arg_0], rbx
0x140010819  mov     [rsp+arg_8], rsi
0x14001081e  push    rdi
0x14001081f  sub     rsp, 20h
0x140010823  mov     rax, [rdx+0B8h]
0x14001082a  mov     rbx, rcx
0x14001082d  cmp     dword ptr [rax+10h], 58h ; 'X'
0x140010831  jnb     short loc_14001083A
0x140010833  mov     eax, 0C000000Dh
0x140010838  jmp     short loc_140010881
0x14001083a  mov     rsi, [rdx+18h]
0x14001083e  xor     edi, edi
0x140010840  call    ?VmpAcquireAll@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpAcquireAll(VM_ROOT_EXTENSION *)
0x140010845  lea     rdx, [rbx+0D0h]
0x14001084c  mov     rcx, [rdx]
0x14001084f  cmp     rcx, rdx
0x140010852  jz      short loc_140010877
0x140010854  cmp     [rcx+18Ah], dil
0x14001085b  jnz     short loc_14001086D
0x14001085d  mov     eax, [rsi]
0x14001085f  cmp     [rcx+160h], eax
0x140010865  jnz     short loc_14001086D
0x140010867  cmp     [rcx+70h], dil
0x14001086b  jnz     short loc_140010872
0x14001086d  mov     rcx, [rcx]
0x140010870  jmp     short loc_14001084F
0x140010872  mov     edi, 0C00000BBh
0x140010877  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x14001087a  call    ?VmpReleaseAll@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseAll(VM_ROOT_EXTENSION *)
0x14001087f  mov     eax, edi
0x140010881  mov     rbx, [rsp+28h+arg_0]
0x140010886  mov     rsi, [rsp+28h+arg_8]
0x14001088b  add     rsp, 20h
0x14001088f  pop     rdi
0x140010890  retn
```
