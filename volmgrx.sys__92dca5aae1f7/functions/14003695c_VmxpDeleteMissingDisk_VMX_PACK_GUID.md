# VmxpDeleteMissingDisk(VMX_PACK *,_GUID *)

- ea: `0x14003695c`
- end: `0x140036ba4`
- name: `?VmxpDeleteMissingDisk@@YAJPEAVVMX_PACK@@PEAU_GUID@@@Z`
- size: `584`
- prototype: `__int64 __fastcall(struct VMX_PACK *this, struct _GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003677c`

## callees

- `0x1400099d8`
- `0x14001b9a0`
- `0x14002a3f4`
- `0x14003695c`
- `0x14003acbc`
- `0x14004a70c`
- `0x14004bac0`
- `0x1400557e4`
- `0x1400561fc`
- `0x14005d734`

## pseudocode

```c
__int64 __fastcall VmxpDeleteMissingDisk(struct VMX_PACK *this, struct _GUID *a2)
{
  struct VMX_PACK *v3; // rbx
  struct VMX_RECORD *DiskById; // rax
  __int64 v5; // r11
  struct VMX_RECORD *v6; // rsi
  __int64 *v7; // r14
  __int64 *v8; // rdi
  __int64 v9; // rbp
  _QWORD *v10; // rcx
  int v11; // eax
  int v12; // edi
  VMX_NOTIFICATION_QUEUE *v14; // rcx
  __int64 v15; // rdx
  VMX_NOTIFICATION_QUEUE *v16; // rcx
  unsigned int v17; // ebx
  __int64 v18; // rdx
  struct VMX_PACK *v19; // [rsp+50h] [rbp+8h] BYREF

  v19 = this;
  v3 = this;
LABEL_2:
  DiskById = VMX_CONFIG::FindDiskById(*((VMX_CONFIG **)v3 + 2), a2);
  v6 = DiskById;
  if ( !DiskById )
  {
    v16 = WPP_GLOBAL_Control;
    v17 = -1070071800;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v18 = 146;
LABEL_49:
      WPP_SF_d(*((_QWORD *)v16 + 3), v18, WPP_2f8af752156e3401cd435973c831895d_Traceguids, v17);
    }
    return v17;
  }
  v7 = (__int64 *)(v5 + 16);
  v8 = *(__int64 **)(v5 + 16);
  v9 = *((_QWORD *)DiskById + (*((_WORD *)DiskById + 32) & 1) + 5);
  while ( 1 )
  {
    if ( v8 == v7 )
    {
      v11 = *(_DWORD *)(v9 + 96);
      if ( *((_DWORD *)v3 + 10) == 1 )
      {
        if ( (v11 & 0x20) == 0 )
        {
          v16 = WPP_GLOBAL_Control;
          v17 = -1070071798;
          if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
          {
            v18 = 148;
            goto LABEL_49;
          }
          return v17;
        }
        goto LABEL_12;
      }
      if ( (v11 & 0x20) == 0 )
      {
        v12 = VMX_PACK::BeginTransaction(v3);
        if ( v12 < 0 )
          goto LABEL_22;
        v12 = VMX_PACK::RemoveVoterTransaction(v3, v6);
        if ( v12 < 0 )
        {
          VMX_PACK::AbortTransaction(v3);
          goto LABEL_22;
        }
        v12 = VMX_PACK::CommitTransaction((struct VMX_CONFIG **)v3, 0, 1);
        if ( v12 < 0 )
        {
LABEL_22:
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
          {
LABEL_27:
            if ( (v12 == -1070071728 || v12 == -1070071804) && VmxpRecoverPackConfigOnline(v3, &v19) >= 0 )
            {
              v3 = v19;
              goto LABEL_2;
            }
            return (unsigned int)v12;
          }
          v15 = 149;
LABEL_26:
          WPP_SF_d(*((_QWORD *)v14 + 3), v15, WPP_2f8af752156e3401cd435973c831895d_Traceguids, (unsigned int)v12);
          goto LABEL_27;
        }
      }
LABEL_12:
      v12 = VMX_PACK::BeginTransaction(v3);
      if ( v12 >= 0 )
      {
        v12 = VMX_PACK::RemoveDiskTransaction(v3, v6);
        if ( v12 < 0 )
        {
          VMX_PACK::AbortTransaction(v3);
        }
        else
        {
          v12 = VMX_PACK::CommitTransaction((struct VMX_CONFIG **)v3, 0, 1);
          if ( v12 >= 0 )
            return 0;
        }
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        goto LABEL_27;
      }
      v15 = 150;
      goto LABEL_26;
    }
    if ( *((_WORD *)v8 + 16) == 3 )
    {
      v10 = v8 + 6;
      if ( (v8[8] & 1) == 0 )
        v10 = v8 + 5;
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD, struct VMX_RECORD *))(*(_QWORD *)*v10 + 80LL))(*v10, v6) )
        break;
    }
    v8 = (__int64 *)*v8;
  }
  v16 = WPP_GLOBAL_Control;
  v17 = -1070071790;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    v18 = 147;
    goto LABEL_49;
  }
  return v17;
}

```

## disassembly

```asm
0x14003695c  mov     [rsp+arg_8], rbx
0x140036961  mov     [rsp+arg_10], rbp
0x140036966  push    rsi
0x140036967  push    rdi
0x140036968  push    r13
0x14003696a  push    r14
0x14003696c  push    r15
0x14003696e  sub     rsp, 20h
0x140036972  mov     r15, rdx
0x140036975  mov     [rsp+48h+arg_0], rcx
0x14003697a  mov     rbx, rcx
0x14003697d  lea     r13, WPP_GLOBAL_Control
0x140036984  mov     r11, [rbx+10h]
0x140036988  mov     rdx, r15; struct _GUID *
0x14003698b  mov     rcx, r11; this
0x14003698e  call    ?FindDiskById@VMX_CONFIG@@QEAAPEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_CONFIG::FindDiskById(_GUID *)
0x140036993  mov     rsi, rax
0x140036996  test    rax, rax
0x140036999  jz      loc_140036B53
0x14003699f  movzx   ecx, word ptr [rax+40h]
0x1400369a3  lea     r14, [r11+10h]
0x1400369a7  mov     rdi, [r14]
0x1400369aa  and     ecx, 1
0x1400369ad  mov     rbp, [rax+rcx*8+28h]
0x1400369b2  cmp     rdi, r14
0x1400369b5  jz      short loc_1400369EB
0x1400369b7  cmp     word ptr [rdi+20h], 3
0x1400369bc  jnz     short loc_1400369E6
0x1400369be  test    byte ptr [rdi+40h], 1
0x1400369c2  lea     rcx, [rdi+30h]
0x1400369c6  jnz     short loc_1400369CC
0x1400369c8  lea     rcx, [rdi+28h]
0x1400369cc  mov     rcx, [rcx]
0x1400369cf  mov     rdx, rsi
0x1400369d2  mov     rax, [rcx]
0x1400369d5  mov     rax, [rax+50h]
0x1400369d9  call    _guard_dispatch_icall
0x1400369de  test    al, al
0x1400369e0  jnz     loc_140036B03
0x1400369e6  mov     rdi, [rdi]
0x1400369e9  jmp     short loc_1400369B2
0x1400369eb  cmp     dword ptr [rbx+28h], 1
0x1400369ef  mov     eax, [rbp+60h]
0x1400369f2  jnz     short loc_140036A41
0x1400369f4  test    al, 20h
0x1400369f6  jz      loc_140036B29
0x1400369fc  mov     rcx, rbx; this
0x1400369ff  call    ?BeginTransaction@VMX_PACK@@QEAAJXZ; VMX_PACK::BeginTransaction(void)
0x140036a04  mov     edi, eax
0x140036a06  test    eax, eax
0x140036a08  js      loc_140036AE3
0x140036a0e  mov     rdx, rsi; struct VMX_RECORD *
0x140036a11  mov     rcx, rbx; this
0x140036a14  call    ?RemoveDiskTransaction@VMX_PACK@@QEAAJPEAVVMX_RECORD@@@Z; VMX_PACK::RemoveDiskTransaction(VMX_RECORD *)
0x140036a19  mov     edi, eax
0x140036a1b  mov     rcx, rbx; this
0x140036a1e  test    eax, eax
0x140036a20  js      loc_140036ADE
0x140036a26  mov     r8b, 1; unsigned __int8
0x140036a29  xor     edx, edx; unsigned __int8
0x140036a2b  call    ?CommitTransaction@VMX_PACK@@QEAAJEE@Z; VMX_PACK::CommitTransaction(uchar,uchar)
0x140036a30  mov     edi, eax
0x140036a32  test    eax, eax
0x140036a34  js      loc_140036AE3
0x140036a3a  xor     eax, eax
0x140036a3c  jmp     loc_140036B8C
0x140036a41  test    al, 20h
0x140036a43  jnz     short loc_1400369FC
0x140036a45  mov     rcx, rbx; this
0x140036a48  call    ?BeginTransaction@VMX_PACK@@QEAAJXZ; VMX_PACK::BeginTransaction(void)
0x140036a4d  mov     edi, eax
0x140036a4f  test    eax, eax
0x140036a51  js      short loc_140036A7E
0x140036a53  mov     rdx, rsi; struct VMX_RECORD *
0x140036a56  mov     rcx, rbx; this
0x140036a59  call    ?RemoveVoterTransaction@VMX_PACK@@QEAAJPEAVVMX_RECORD@@@Z; VMX_PACK::RemoveVoterTransaction(VMX_RECORD *)
0x140036a5e  mov     edi, eax
0x140036a60  mov     rcx, rbx; this
0x140036a63  test    eax, eax
0x140036a65  js      short loc_140036A79
0x140036a67  mov     r8b, 1; unsigned __int8
0x140036a6a  xor     edx, edx; unsigned __int8
0x140036a6c  call    ?CommitTransaction@VMX_PACK@@QEAAJEE@Z; VMX_PACK::CommitTransaction(uchar,uchar)
0x140036a71  mov     edi, eax
0x140036a73  test    eax, eax
0x140036a75  jns     short loc_1400369FC
0x140036a77  jmp     short loc_140036A7E
0x140036a79  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x140036a7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140036a85  cmp     rcx, r13
0x140036a88  jz      short loc_140036AAF
0x140036a8a  mov     eax, [rcx+2Ch]
0x140036a8d  test    al, 8
0x140036a8f  jz      short loc_140036AAF
0x140036a91  cmp     byte ptr [rcx+29h], 2
0x140036a95  jb      short loc_140036AAF
0x140036a97  mov     edx, 95h
0x140036a9c  mov     rcx, [rcx+18h]
0x140036aa0  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x140036aa7  mov     r9d, edi
0x140036aaa  call    WPP_SF_d
0x140036aaf  cmp     edi, 0C0380050h
0x140036ab5  jz      short loc_140036AC3
0x140036ab7  cmp     edi, 0C0380004h
0x140036abd  jnz     loc_140036B4F
0x140036ac3  lea     rdx, [rsp+48h+arg_0]; struct VMX_PACK **
0x140036ac8  mov     rcx, rbx; struct VMX_PACK *
0x140036acb  call    ?VmxpRecoverPackConfigOnline@@YAJPEAVVMX_PACK@@PEAPEAV1@@Z; VmxpRecoverPackConfigOnline(VMX_PACK *,VMX_PACK * *)
0x140036ad0  test    eax, eax
0x140036ad2  js      short loc_140036B4F
0x140036ad4  mov     rbx, [rsp+48h+arg_0]
0x140036ad9  jmp     loc_140036984
0x140036ade  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x140036ae3  mov     rcx, cs:WPP_GLOBAL_Control
0x140036aea  cmp     rcx, r13
0x140036aed  jz      short loc_140036AAF
0x140036aef  mov     eax, [rcx+2Ch]
0x140036af2  test    al, 2
0x140036af4  jz      short loc_140036AAF
0x140036af6  cmp     byte ptr [rcx+29h], 2
0x140036afa  jb      short loc_140036AAF
0x140036afc  mov     edx, 96h
0x140036b01  jmp     short loc_140036A9C
0x140036b03  mov     rcx, cs:WPP_GLOBAL_Control
0x140036b0a  mov     ebx, 0C0380012h
0x140036b0f  cmp     rcx, r13
0x140036b12  jz      short loc_140036B8A
0x140036b14  mov     edx, [rcx+2Ch]
0x140036b17  test    dl, 2
0x140036b1a  jz      short loc_140036B8A
0x140036b1c  cmp     byte ptr [rcx+29h], 2
0x140036b20  jb      short loc_140036B8A
0x140036b22  mov     edx, 93h
0x140036b27  jmp     short loc_140036B77
0x140036b29  mov     rcx, cs:WPP_GLOBAL_Control
0x140036b30  mov     ebx, 0C038000Ah
0x140036b35  cmp     rcx, r13
0x140036b38  jz      short loc_140036B8A
0x140036b3a  mov     edx, [rcx+2Ch]
0x140036b3d  test    dl, 2
0x140036b40  jz      short loc_140036B8A
0x140036b42  cmp     byte ptr [rcx+29h], 2
0x140036b46  jb      short loc_140036B8A
0x140036b48  mov     edx, 94h
0x140036b4d  jmp     short loc_140036B77
0x140036b4f  mov     eax, edi
0x140036b51  jmp     short loc_140036B8C
0x140036b53  mov     rcx, cs:WPP_GLOBAL_Control
0x140036b5a  mov     ebx, 0C0380008h
0x140036b5f  cmp     rcx, r13
0x140036b62  jz      short loc_140036B8A
0x140036b64  mov     edx, [rcx+2Ch]
0x140036b67  test    dl, 2
0x140036b6a  jz      short loc_140036B8A
0x140036b6c  cmp     byte ptr [rcx+29h], 2
0x140036b70  jb      short loc_140036B8A
0x140036b72  mov     edx, 92h
0x140036b77  mov     rcx, [rcx+18h]
0x140036b7b  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x140036b82  mov     r9d, ebx
0x140036b85  call    WPP_SF_d
0x140036b8a  mov     eax, ebx
0x140036b8c  mov     rbx, [rsp+48h+arg_8]
0x140036b91  mov     rbp, [rsp+48h+arg_10]
0x140036b96  add     rsp, 20h
0x140036b9a  pop     r15
0x140036b9c  pop     r14
0x140036b9e  pop     r13
0x140036ba0  pop     rdi
0x140036ba1  pop     rsi
0x140036ba2  retn
```
