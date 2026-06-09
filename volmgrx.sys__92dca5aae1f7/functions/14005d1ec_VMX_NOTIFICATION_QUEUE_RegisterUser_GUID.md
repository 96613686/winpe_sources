# VMX_NOTIFICATION_QUEUE::RegisterUser(_GUID *)

- ea: `0x14005d1ec`
- end: `0x14005d405`
- name: `?RegisterUser@VMX_NOTIFICATION_QUEUE@@QEAAJPEAU_GUID@@@Z`
- size: `537`
- prototype: `__int64 __fastcall(VMX_NOTIFICATION_QUEUE *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14005d118`

## callees

- `0x140005f80`
- `0x1400099d8`
- `0x14001b334`
- `0x14001b9a0`
- `0x14001be80`
- `0x140029204`
- `0x14005d1ec`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x14005d31d`
- `ntoskrnl!ExUuidCreate` at `0x14005d31d`

## pseudocode

```c
__int64 __fastcall VMX_NOTIFICATION_QUEUE::RegisterUser(VMX_NOTIFICATION_QUEUE *this, struct _GUID *a2)
{
  VMX_GLOBAL_DATA *v2; // r15
  char *v3; // rsi
  char v4; // r8
  unsigned int v5; // r14d
  __int64 v8; // rdi
  VMX_USER_ENTRY *v9; // rax
  __int64 v10; // rbx
  VMX_USER_ENTRY **v11; // rbp
  VMX_USER_ENTRY **v12; // rcx
  VMX_NOTIFICATION_QUEUE *v13; // rcx
  unsigned int v14; // ebx
  __int64 v15; // rdx
  struct _GUID *v16; // rax
  struct _GUID *v17; // rbx
  unsigned int v18; // edx
  NTSTATUS v19; // ebp
  __int64 result; // rax
  char **v21; // rax

  v2 = Global;
  v3 = (char *)this + 40;
  v4 = 0;
  *a2 = GUID_NULL;
  v5 = 0;
  v8 = MEMORY[0xFFFFF78000000014];
  v9 = (VMX_USER_ENTRY *)*((_QWORD *)this + 5);
  v10 = MEMORY[0xFFFFF78000000014] - 600000000LL;
  if ( v9 != (VMX_NOTIFICATION_QUEUE *)((char *)this + 40) )
  {
    do
    {
      v11 = *(VMX_USER_ENTRY ***)v9;
      if ( *((_QWORD *)v9 + 5) || *((_QWORD *)v9 + 6) >= v10 )
      {
        ++v5;
      }
      else
      {
        if ( v11[1] != v9 )
          goto LABEL_24;
        v12 = (VMX_USER_ENTRY **)*((_QWORD *)v9 + 1);
        if ( *v12 != v9 )
          goto LABEL_24;
        *v12 = (VMX_USER_ENTRY *)v11;
        v11[1] = (VMX_USER_ENTRY *)v12;
        VMX_USER_ENTRY::`scalar deleting destructor'(v9, (unsigned int)a2);
        (*((void (__fastcall **)(_QWORD))v2 + 8))(*((_QWORD *)v2 + 1));
        v4 = 1;
      }
      v9 = (VMX_USER_ENTRY *)v11;
    }
    while ( v11 != (VMX_USER_ENTRY **)v3 );
    if ( v4 )
      VMX_NOTIFICATION_QUEUE::CleanNotificationQueue(this);
    if ( v5 >= 5 )
    {
      v13 = WPP_GLOBAL_Control;
      v14 = -1070071774;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return v14;
      }
      v15 = 10;
LABEL_30:
      WPP_SF_d(*((_QWORD *)v13 + 3), v15, WPP_ff83fa8e29b93af5710e31e1bccf8937_Traceguids, v14);
      return v14;
    }
  }
  v16 = (struct _GUID *)VMX_ALLOCATED_OBJECT::operator new(0x40u, 0x42u, 0x65556D56u);
  v17 = v16;
  if ( !v16 )
  {
    v13 = WPP_GLOBAL_Control;
    v14 = -1073741670;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return v14;
    }
    v15 = 11;
    goto LABEL_30;
  }
  memset(v16, 0, 0x40u);
  v17[2].Data1 = *(_DWORD *)this - 1;
  v19 = ExUuidCreate(v17 + 1);
  if ( v19 >= 0 )
  {
    *(_QWORD *)&v17[3].Data1 = v8;
    v21 = (char **)*((_QWORD *)v3 + 1);
    if ( *v21 != v3 )
LABEL_24:
      __fastfail(3u);
    *(_QWORD *)&v17->Data1 = v3;
    *(_QWORD *)v17->Data4 = v21;
    *v21 = (char *)v17;
    *((_QWORD *)v3 + 1) = v17;
    (*((void (__fastcall **)(_QWORD))v2 + 7))(*((_QWORD *)v2 + 1));
    result = 0;
    *a2 = v17[1];
  }
  else
  {
    VMX_USER_ENTRY::`scalar deleting destructor'((VMX_USER_ENTRY *)v17, v18);
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        12,
        WPP_ff83fa8e29b93af5710e31e1bccf8937_Traceguids,
        (unsigned int)v19);
    }
    return (unsigned int)v19;
  }
  return result;
}

```

## disassembly

```asm
0x14005d1ec  push    rbx
0x14005d1ee  push    rbp
0x14005d1ef  push    rsi
0x14005d1f0  push    rdi
0x14005d1f1  push    r12
0x14005d1f3  push    r13
0x14005d1f5  push    r14
0x14005d1f7  push    r15
0x14005d1f9  sub     rsp, 28h
0x14005d1fd  movups  xmm0, xmmword ptr cs:?GUID_NULL@@3U_GUID@@B.Data1; _GUID const GUID_NULL ...
0x14005d204  mov     r15, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14005d20b  lea     rsi, [rcx+28h]
0x14005d20f  mov     rdi, 0FFFFF78000000014h
0x14005d219  xor     r8b, r8b
0x14005d21c  movdqu  xmmword ptr [rdx], xmm0
0x14005d220  xor     r14d, r14d
0x14005d223  mov     r13, rdx
0x14005d226  mov     r12, rcx
0x14005d229  mov     rdi, [rdi]
0x14005d22c  mov     rax, [rsi]
0x14005d22f  lea     rbx, [rdi-23C34600h]
0x14005d236  cmp     rax, rsi
0x14005d239  jz      loc_14005D2E2
0x14005d23f  cmp     qword ptr [rax+28h], 0
0x14005d244  mov     rbp, [rax]
0x14005d247  jnz     short loc_14005D287
0x14005d249  cmp     [rax+30h], rbx
0x14005d24d  jge     short loc_14005D287
0x14005d24f  cmp     [rbp+8], rax
0x14005d253  jnz     loc_14005D382
0x14005d259  mov     rcx, [rax+8]
0x14005d25d  cmp     [rcx], rax
0x14005d260  jnz     loc_14005D382
0x14005d266  mov     [rcx], rbp
0x14005d269  mov     [rbp+8], rcx
0x14005d26d  mov     rcx, rax; this
0x14005d270  call    ??_GVMX_USER_ENTRY@@QEAAPEAXI@Z; VMX_USER_ENTRY::`scalar deleting destructor'(uint)
0x14005d275  mov     rax, [r15+40h]
0x14005d279  mov     rcx, [r15+8]
0x14005d27d  call    _guard_dispatch_icall
0x14005d282  mov     r8b, 1
0x14005d285  jmp     short loc_14005D28A
0x14005d287  inc     r14d
0x14005d28a  mov     rax, rbp
0x14005d28d  cmp     rbp, rsi
0x14005d290  jnz     short loc_14005D23F
0x14005d292  test    r8b, r8b
0x14005d295  jz      short loc_14005D29F
0x14005d297  mov     rcx, r12; this
0x14005d29a  call    ?CleanNotificationQueue@VMX_NOTIFICATION_QUEUE@@QEAAXXZ; VMX_NOTIFICATION_QUEUE::CleanNotificationQueue(void)
0x14005d29f  cmp     r14d, 5
0x14005d2a3  jb      short loc_14005D2E2
0x14005d2a5  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d2ac  lea     rax, WPP_GLOBAL_Control
0x14005d2b3  mov     ebx, 0C0380022h
0x14005d2b8  cmp     rcx, rax
0x14005d2bb  jz      loc_14005D3F1
0x14005d2c1  test    dword ptr [rcx+2Ch], 400h
0x14005d2c8  jz      loc_14005D3F1
0x14005d2ce  cmp     byte ptr [rcx+29h], 2
0x14005d2d2  jb      loc_14005D3F1
0x14005d2d8  mov     edx, 0Ah
0x14005d2dd  jmp     loc_14005D3DE
0x14005d2e2  mov     edx, 42h ; 'B'; unsigned __int64
0x14005d2e7  mov     r8d, 65556D56h; unsigned int
0x14005d2ed  lea     ebp, [rdx-2]
0x14005d2f0  mov     ecx, ebp; unsigned __int64
0x14005d2f2  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14005d2f7  mov     rbx, rax
0x14005d2fa  test    rax, rax
0x14005d2fd  jz      loc_14005D3B2
0x14005d303  mov     r8d, ebp; Size
0x14005d306  xor     edx, edx; Val
0x14005d308  mov     rcx, rax; void *
0x14005d30b  call    memset
0x14005d310  mov     ecx, [r12]
0x14005d314  dec     ecx
0x14005d316  mov     [rbx+20h], ecx
0x14005d319  lea     rcx, [rbx+10h]; Uuid
0x14005d31d  call    cs:__imp_ExUuidCreate
0x14005d324  nop     dword ptr [rax+rax+00h]
0x14005d329  mov     ebp, eax
0x14005d32b  test    eax, eax
0x14005d32d  jns     short loc_14005D375
0x14005d32f  mov     rcx, rbx; this
0x14005d332  call    ??_GVMX_USER_ENTRY@@QEAAPEAXI@Z; VMX_USER_ENTRY::`scalar deleting destructor'(uint)
0x14005d337  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d33e  lea     rax, WPP_GLOBAL_Control
0x14005d345  cmp     rcx, rax
0x14005d348  jz      short loc_14005D371
0x14005d34a  test    dword ptr [rcx+2Ch], 400h
0x14005d351  jz      short loc_14005D371
0x14005d353  cmp     byte ptr [rcx+29h], 2
0x14005d357  jb      short loc_14005D371
0x14005d359  mov     rcx, [rcx+18h]
0x14005d35d  lea     r8, WPP_ff83fa8e29b93af5710e31e1bccf8937_Traceguids
0x14005d364  mov     edx, 0Ch
0x14005d369  mov     r9d, ebp
0x14005d36c  call    WPP_SF_d
0x14005d371  mov     eax, ebp
0x14005d373  jmp     short loc_14005D3F3
0x14005d375  mov     [rbx+30h], rdi
0x14005d379  mov     rax, [rsi+8]
0x14005d37d  cmp     [rax], rsi
0x14005d380  jz      short loc_14005D389
0x14005d382  mov     ecx, 3
0x14005d387  int     29h; Win8: RtlFailFast(ecx)
0x14005d389  mov     [rbx], rsi
0x14005d38c  mov     [rbx+8], rax
0x14005d390  mov     [rax], rbx
0x14005d393  mov     [rsi+8], rbx
0x14005d397  mov     rax, [r15+38h]
0x14005d39b  mov     rcx, [r15+8]
0x14005d39f  call    _guard_dispatch_icall
0x14005d3a4  movups  xmm0, xmmword ptr [rbx+10h]
0x14005d3a8  xor     eax, eax
0x14005d3aa  movdqu  xmmword ptr [r13+0], xmm0
0x14005d3b0  jmp     short loc_14005D3F3
0x14005d3b2  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d3b9  lea     rax, WPP_GLOBAL_Control
0x14005d3c0  mov     ebx, 0C000009Ah
0x14005d3c5  cmp     rcx, rax
0x14005d3c8  jz      short loc_14005D3F1
0x14005d3ca  test    dword ptr [rcx+2Ch], 400h
0x14005d3d1  jz      short loc_14005D3F1
0x14005d3d3  cmp     byte ptr [rcx+29h], 2
0x14005d3d7  jb      short loc_14005D3F1
0x14005d3d9  mov     edx, 0Bh
0x14005d3de  mov     rcx, [rcx+18h]
0x14005d3e2  lea     r8, WPP_ff83fa8e29b93af5710e31e1bccf8937_Traceguids
0x14005d3e9  mov     r9d, ebx
0x14005d3ec  call    WPP_SF_d
0x14005d3f1  mov     eax, ebx
0x14005d3f3  add     rsp, 28h
0x14005d3f7  pop     r15
0x14005d3f9  pop     r14
0x14005d3fb  pop     r13
0x14005d3fd  pop     r12
0x14005d3ff  pop     rdi
0x14005d400  pop     rsi
0x14005d401  pop     rbp
0x14005d402  pop     rbx
0x14005d403  retn
```
