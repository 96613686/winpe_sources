# VMX_PACK::CopyPack(VMX_PACK *)

- ea: `0x14004e950`
- end: `0x14004eb1e`
- name: `?CopyPack@VMX_PACK@@QEAAJPEAV1@@Z`
- size: `462`
- prototype: `__int64 __fastcall(VMX_PACK *__hidden this, struct VMX_PACK *)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x14002b13c`
- `0x14002b964`
- `0x14002c3dc`
- `0x14002caf8`

## callees

- `0x140005f80`
- `0x140008d28`
- `0x140008da0`
- `0x1400099d8`
- `0x14002b0c4`
- `0x14003e124`
- `0x1400486c8`
- `0x140048cdc`
- `0x14004e950`

## pseudocode

```c
__int64 __fastcall VMX_PACK::CopyPack(VMX_PACK *this, struct VMX_PACK *a2)
{
  VMX_CONFIG *v4; // rax
  VMX_CONFIG *v5; // rbx
  unsigned int v6; // edx
  int v7; // ebp
  VMX_NOTIFICATION_QUEUE *v8; // r10
  __int64 v9; // rdx
  VMX_LOG *v11; // rax
  VMX_LOG *v12; // rax
  VMX_LOG *v13; // rbx
  unsigned int v14; // edx
  VMX_NOTIFICATION_QUEUE *v15; // r10
  __int64 v16; // rdx

  v4 = (VMX_CONFIG *)VMX_ALLOCATED_OBJECT::operator new(0x38u, 0x102u, 0x6F436D56u);
  v5 = v4;
  if ( !v4 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return 3221225626LL;
    }
    v16 = 21;
    goto LABEL_27;
  }
  *(_QWORD *)v4 = 0;
  *((_QWORD *)v4 + 1) = 0;
  *((_QWORD *)v4 + 4) = 0;
  *((_QWORD *)v4 + 5) = 0;
  *((_QWORD *)v4 + 3) = (char *)v4 + 16;
  *((_QWORD *)v4 + 2) = (char *)v4 + 16;
  *((_QWORD *)v4 + 6) = 1;
  v7 = VMX_CONFIG::CopyConfiguration(v4, *((struct VMX_RAW_CONFIG ***)a2 + 2));
  if ( v7 < 0 )
  {
    VMX_CONFIG::`scalar deleting destructor'(v5, v6);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return (unsigned int)v7;
    }
    v9 = 22;
LABEL_7:
    WPP_SF_d(*((_QWORD *)v8 + 3), v9, WPP_b525482092043ba595507d12d78e6f73_Traceguids, (unsigned int)v7);
    return (unsigned int)v7;
  }
  *(_QWORD *)v5 = this;
  *((_QWORD *)this + 2) = v5;
  if ( !*((_QWORD *)a2 + 3) )
    goto LABEL_18;
  v11 = (VMX_LOG *)VMX_ALLOCATED_OBJECT::operator new(0x128u, 0x42u, 0x6F4C6D56u);
  if ( v11 )
  {
    v12 = VMX_LOG::VMX_LOG(v11);
    v13 = v12;
    if ( v12 )
    {
      v7 = VMX_LOG::CopyLog(v12, *((struct VMX_LOG **)a2 + 3));
      if ( v7 < 0 )
      {
        VMX_LOG::`scalar deleting destructor'(v13, v14);
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
        {
          return (unsigned int)v7;
        }
        v9 = 24;
        goto LABEL_7;
      }
      *((_QWORD *)this + 3) = v13;
LABEL_18:
      *((_BYTE *)this + 56) = *((_BYTE *)a2 + 56);
      *((_BYTE *)this + 57) = *((_BYTE *)a2 + 57);
      VMX_PACK::UpdateCounters(this);
      return 0;
    }
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    v16 = 23;
LABEL_27:
    WPP_SF_d(*((_QWORD *)v15 + 3), v16, WPP_b525482092043ba595507d12d78e6f73_Traceguids, 3221225626LL);
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14004e950  push    rbx
0x14004e952  push    rbp
0x14004e953  push    rsi
0x14004e954  push    rdi
0x14004e955  sub     rsp, 28h
0x14004e959  mov     rsi, rdx
0x14004e95c  mov     rdi, rcx
0x14004e95f  mov     edx, 102h; unsigned __int64
0x14004e964  mov     ecx, 38h ; '8'; unsigned __int64
0x14004e969  mov     r8d, 6F436D56h; unsigned int
0x14004e96f  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14004e974  mov     rbx, rax
0x14004e977  test    rax, rax
0x14004e97a  jz      loc_14004EAD2
0x14004e980  mov     qword ptr [rax], 0
0x14004e987  lea     rcx, [rax+10h]
0x14004e98b  mov     qword ptr [rax+8], 0
0x14004e993  mov     qword ptr [rax+20h], 0
0x14004e99b  mov     qword ptr [rax+28h], 0
0x14004e9a3  mov     [rcx+8], rcx
0x14004e9a7  mov     [rcx], rcx
0x14004e9aa  mov     rcx, rax; this
0x14004e9ad  mov     qword ptr [rax+30h], 1
0x14004e9b5  mov     rdx, [rsi+10h]; struct VMX_CONFIG *
0x14004e9b9  call    ?CopyConfiguration@VMX_CONFIG@@QEAAJPEAV1@@Z; VMX_CONFIG::CopyConfiguration(VMX_CONFIG *)
0x14004e9be  mov     ebp, eax
0x14004e9c0  test    eax, eax
0x14004e9c2  jns     short loc_14004EA0E
0x14004e9c4  mov     rcx, rbx; this
0x14004e9c7  call    ??_GVMX_CONFIG@@QEAAPEAXI@Z; VMX_CONFIG::`scalar deleting destructor'(uint)
0x14004e9cc  mov     r10, cs:WPP_GLOBAL_Control
0x14004e9d3  lea     rcx, WPP_GLOBAL_Control
0x14004e9da  cmp     r10, rcx
0x14004e9dd  jz      short loc_14004EA07
0x14004e9df  mov     edx, [r10+2Ch]
0x14004e9e3  test    dl, 8
0x14004e9e6  jz      short loc_14004EA07
0x14004e9e8  cmp     byte ptr [r10+29h], 2
0x14004e9ed  jb      short loc_14004EA07
0x14004e9ef  mov     edx, 16h
0x14004e9f4  mov     rcx, [r10+18h]
0x14004e9f8  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x14004e9ff  mov     r9d, ebp
0x14004ea02  call    WPP_SF_d
0x14004ea07  mov     eax, ebp
0x14004ea09  jmp     loc_14004EB14
0x14004ea0e  mov     [rbx], rdi
0x14004ea11  mov     [rdi+10h], rbx
0x14004ea15  cmp     qword ptr [rsi+18h], 0
0x14004ea1a  jz      short loc_14004EA91
0x14004ea1c  mov     edx, 42h ; 'B'; unsigned __int64
0x14004ea21  mov     ecx, 128h; unsigned __int64
0x14004ea26  mov     r8d, 6F4C6D56h; unsigned int
0x14004ea2c  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14004ea31  test    rax, rax
0x14004ea34  jz      short loc_14004EAA9
0x14004ea36  mov     rcx, rax; this
0x14004ea39  call    ??0VMX_LOG@@QEAA@XZ; VMX_LOG::VMX_LOG(void)
0x14004ea3e  mov     rbx, rax
0x14004ea41  test    rax, rax
0x14004ea44  jz      short loc_14004EAA9
0x14004ea46  mov     rdx, [rsi+18h]; struct VMX_LOG *
0x14004ea4a  mov     rcx, rax; this
0x14004ea4d  call    ?CopyLog@VMX_LOG@@QEAAJPEAV1@@Z; VMX_LOG::CopyLog(VMX_LOG *)
0x14004ea52  mov     ebp, eax
0x14004ea54  test    eax, eax
0x14004ea56  jns     short loc_14004EA8D
0x14004ea58  mov     rcx, rbx; this
0x14004ea5b  call    ??_GVMX_LOG@@QEAAPEAXI@Z; VMX_LOG::`scalar deleting destructor'(uint)
0x14004ea60  mov     r10, cs:WPP_GLOBAL_Control
0x14004ea67  lea     rcx, WPP_GLOBAL_Control
0x14004ea6e  cmp     r10, rcx
0x14004ea71  jz      short loc_14004EA07
0x14004ea73  mov     edx, [r10+2Ch]
0x14004ea77  test    dl, 8
0x14004ea7a  jz      short loc_14004EA07
0x14004ea7c  cmp     byte ptr [r10+29h], 2
0x14004ea81  jb      short loc_14004EA07
0x14004ea83  mov     edx, 18h
0x14004ea88  jmp     loc_14004E9F4
0x14004ea8d  mov     [rdi+18h], rbx
0x14004ea91  mov     al, [rsi+38h]
0x14004ea94  mov     rcx, rdi; this
0x14004ea97  mov     [rdi+38h], al
0x14004ea9a  mov     al, [rsi+39h]
0x14004ea9d  mov     [rdi+39h], al
0x14004eaa0  call    ?UpdateCounters@VMX_PACK@@QEAAXXZ; VMX_PACK::UpdateCounters(void)
0x14004eaa5  xor     eax, eax
0x14004eaa7  jmp     short loc_14004EB14
0x14004eaa9  mov     r10, cs:WPP_GLOBAL_Control
0x14004eab0  lea     rcx, WPP_GLOBAL_Control
0x14004eab7  cmp     r10, rcx
0x14004eaba  jz      short loc_14004EB0F
0x14004eabc  mov     eax, [r10+2Ch]
0x14004eac0  test    al, 8
0x14004eac2  jz      short loc_14004EB0F
0x14004eac4  cmp     byte ptr [r10+29h], 2
0x14004eac9  jb      short loc_14004EB0F
0x14004eacb  mov     edx, 17h
0x14004ead0  jmp     short loc_14004EAF9
0x14004ead2  mov     r10, cs:WPP_GLOBAL_Control
0x14004ead9  lea     rcx, WPP_GLOBAL_Control
0x14004eae0  cmp     r10, rcx
0x14004eae3  jz      short loc_14004EB0F
0x14004eae5  mov     eax, [r10+2Ch]
0x14004eae9  test    al, 8
0x14004eaeb  jz      short loc_14004EB0F
0x14004eaed  cmp     byte ptr [r10+29h], 2
0x14004eaf2  jb      short loc_14004EB0F
0x14004eaf4  mov     edx, 15h
0x14004eaf9  mov     rcx, [r10+18h]
0x14004eafd  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x14004eb04  mov     r9d, 0C000009Ah
0x14004eb0a  call    WPP_SF_d
0x14004eb0f  mov     eax, 0C000009Ah
0x14004eb14  add     rsp, 28h
0x14004eb18  pop     rdi
0x14004eb19  pop     rsi
0x14004eb1a  pop     rbp
0x14004eb1b  pop     rbx
0x14004eb1c  retn
```
