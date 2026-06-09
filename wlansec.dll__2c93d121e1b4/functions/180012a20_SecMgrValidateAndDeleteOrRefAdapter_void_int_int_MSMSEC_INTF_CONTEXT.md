# SecMgrValidateAndDeleteOrRefAdapter(void *,int,int,MSMSEC_INTF_CONTEXT * *)

- ea: `0x180012a20`
- end: `0x180012de1`
- name: `?SecMgrValidateAndDeleteOrRefAdapter@@YAKPEAXHHPEAPEAUMSMSEC_INTF_CONTEXT@@@Z`
- size: `961`
- prototype: `unsigned int __fastcall(void *, int, int, struct MSMSEC_INTF_CONTEXT **)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x180003b78`
- `0x1800115c0`
- `0x1800125b0`
- `0x180012970`

## callees

- `0x180004518`
- `0x1800063b0`
- `0x18000892c`
- `0x180008998`
- `0x180012a20`
- `0x180055a38`
- `0x180057f50`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180012b64`
- `MobileNetworking!ReleaseWriteLock` at `0x180012b64`
- `MobileNetworking!AcquireWriteLock` at `0x180012ab7`
- `MobileNetworking!AcquireWriteLock` at `0x180012ab7`

## string_xrefs

- `0x180012aa2`: `SecMgrValidateAndDeleteOrRefAdapter`
- `0x180012b4f`: `SecMgrValidateAndDeleteOrRefAdapter`
- `0x180012d9f`: `SecMgrValidateAndDeleteOrRefAdapter`

## pseudocode

```c
__int64 __fastcall SecMgrValidateAndDeleteOrRefAdapter(void ***a1, int a2, int a3, void ****a4)
{
  PVOID *v8; // rcx
  int v9; // r8d
  __int64 *v10; // rax
  unsigned int v11; // ebx
  PVOID *v12; // rbx
  __int64 v13; // r9
  void **v15; // rax
  void **v16; // rcx
  void **v17; // rax
  __int64 v18; // rdx

  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 16, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 17) & 0x800) != 0 )
    {
      WPP_SF_q(v8[7], 17, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, a1);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( a2 && a3 )
  {
    v11 = 1359;
    if ( v8 == &WPP_GLOBAL_Control )
      return v11;
    if ( (*((_BYTE *)v8 + 68) & 1) == 0 )
      goto LABEL_28;
    v18 = 18;
    goto LABEL_47;
  }
  if ( a1 && a4 && !*a4 )
  {
    AcquireWriteLock(&g_MSMSecState, qword_1800AEFC0, "SecMgrValidateAndDeleteOrRefAdapter", 363);
    v10 = (__int64 *)qword_1800AF028;
    v11 = 1168;
    while ( v10 != &qword_1800AF028 )
    {
      if ( v10 == (__int64 *)a1 )
      {
        if ( a2 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
            WPP_SF_qDDDDDD(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              20,
              *((unsigned __int8 *)a1 + 2364),
              a1,
              *((unsigned __int8 *)a1 + 2360),
              *((unsigned __int8 *)a1 + 2361),
              *((unsigned __int8 *)a1 + 2362),
              *((unsigned __int8 *)a1 + 2363),
              *((unsigned __int8 *)a1 + 2364),
              *((unsigned __int8 *)a1 + 2365));
          v15 = *a1;
          if ( (*a1)[1] != a1
            || (v16 = a1[1], *v16 != a1)
            || (*v16 = v15,
                v15[1] = v16,
                v17 = (void **)qword_1800AF040,
                *(__int64 **)qword_1800AF040 != &qword_1800AF038) )
          {
            __fastfail(3u);
          }
          *a1 = (void **)&qword_1800AF038;
          a1[1] = v17;
          *v17 = a1;
          qword_1800AF040 = (__int64)a1;
        }
        else if ( a3 )
        {
          v12 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
            {
              WPP_SF_Ls(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, v9, *((_DWORD *)a1 + 624), (__int64)">>> Refing >>>");
              v12 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x400) != 0 )
              WPP_SF_sdqDDDDDD(
                (unsigned int)v12[7],
                12,
                (unsigned int)&WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids,
                (unsigned int)"SecMgrValidateAndDeleteOrRefAdapter",
                135,
                (char)a1,
                *((_BYTE *)a1 + 2360),
                *((_BYTE *)a1 + 2361),
                *((_BYTE *)a1 + 2362),
                *((_BYTE *)a1 + 2363),
                *((_BYTE *)a1 + 2364),
                *((_BYTE *)a1 + 2365));
          }
          v13 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)a1 + 4);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v13);
        }
        v11 = 0;
        *a4 = a1;
        break;
      }
      v10 = (__int64 *)*v10;
    }
    ReleaseWriteLock(&g_MSMSecState, qword_1800AEFC0, "SecMgrValidateAndDeleteOrRefAdapter", 402);
    goto LABEL_27;
  }
  v11 = 87;
  if ( v8 == &WPP_GLOBAL_Control )
    return v11;
  if ( (*((_BYTE *)v8 + 68) & 1) != 0 )
  {
    v18 = 19;
LABEL_47:
    WPP_SF_(v8[7], v18, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
LABEL_27:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_28:
  if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 17) & 0x100) != 0 )
    WPP_SF_d(v8[7], 21, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180012a20  mov     [rsp+arg_8], rbp
0x180012a25  mov     [rsp+arg_10], rsi
0x180012a2a  push    rdi
0x180012a2b  push    r14
0x180012a2d  push    r15
0x180012a2f  sub     rsp, 60h
0x180012a33  mov     rsi, r9
0x180012a36  mov     r14d, r8d
0x180012a39  mov     ebp, edx
0x180012a3b  mov     rdi, rcx
0x180012a3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a45  lea     r15, WPP_GLOBAL_Control
0x180012a4c  cmp     rcx, r15
0x180012a4f  jz      short loc_180012A70
0x180012a51  test    dword ptr [rcx+44h], 100h
0x180012a58  jnz     loc_180012CC7
0x180012a5e  cmp     rcx, r15
0x180012a61  jz      short loc_180012A70
0x180012a63  test    dword ptr [rcx+44h], 800h
0x180012a6a  jnz     loc_180012CE8
0x180012a70  mov     [rsp+78h+arg_0], rbx
0x180012a78  test    ebp, ebp
0x180012a7a  jnz     loc_180012C19
0x180012a80  test    rdi, rdi
0x180012a83  jz      loc_180012B9F
0x180012a89  test    rsi, rsi
0x180012a8c  jz      loc_180012B9F
0x180012a92  cmp     qword ptr [rsi], 0
0x180012a96  jnz     loc_180012B9F
0x180012a9c  mov     r9d, 16Bh
0x180012aa2  lea     r8, aSecmgrvalidate_1; "SecMgrValidateAndDeleteOrRefAdapter"
0x180012aa9  lea     rdx, qword_1800AEFC0
0x180012ab0  lea     rcx, ?g_MSMSecState@@3UMSMSEC_GLOBAL_STATE@@A; MSMSEC_GLOBAL_STATE g_MSMSecState
0x180012ab7  call    cs:__imp_AcquireWriteLock
0x180012abe  nop     dword ptr [rax+rax+00h]
0x180012ac3  mov     rax, cs:qword_1800AF028
0x180012aca  lea     rcx, qword_1800AF028
0x180012ad1  mov     ebx, 490h
0x180012ad6  cmp     rax, rcx
0x180012ad9  jz      short loc_180012B49
0x180012adb  cmp     rax, rdi
0x180012ade  jnz     loc_180012C11
0x180012ae4  test    ebp, ebp
0x180012ae6  jnz     loc_180012BCE
0x180012aec  test    r14d, r14d
0x180012aef  jz      short loc_180012B44
0x180012af1  mov     rbx, cs:WPP_GLOBAL_Control
0x180012af8  cmp     rbx, r15
0x180012afb  jz      short loc_180012B1C
0x180012afd  test    dword ptr [rbx+44h], 100h
0x180012b04  jnz     loc_180012D22
0x180012b0a  cmp     rbx, r15
0x180012b0d  jz      short loc_180012B1C
0x180012b0f  test    dword ptr [rbx+44h], 400h
0x180012b16  jnz     loc_180012D4F
0x180012b1c  mov     r9d, 1
0x180012b22  lock xadd [rdi+10h], r9d
0x180012b28  inc     r9d
0x180012b2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b32  cmp     rcx, r15
0x180012b35  jz      short loc_180012B44
0x180012b37  test    dword ptr [rcx+44h], 400h
0x180012b3e  jnz     loc_180012DC7
0x180012b44  xor     ebx, ebx
0x180012b46  mov     [rsi], rdi
0x180012b49  mov     r9d, 192h
0x180012b4f  lea     r8, aSecmgrvalidate_1; "SecMgrValidateAndDeleteOrRefAdapter"
0x180012b56  lea     rdx, qword_1800AEFC0
0x180012b5d  lea     rcx, ?g_MSMSecState@@3UMSMSEC_GLOBAL_STATE@@A; MSMSEC_GLOBAL_STATE g_MSMSecState
0x180012b64  call    cs:__imp_ReleaseWriteLock
0x180012b6b  nop     dword ptr [rax+rax+00h]
0x180012b70  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b77  cmp     rcx, r15
0x180012b7a  jz      short loc_180012BAD
0x180012b7c  test    dword ptr [rcx+44h], 100h
0x180012b83  jz      short loc_180012BAD
0x180012b85  mov     rcx, [rcx+38h]
0x180012b89  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180012b90  mov     edx, 15h
0x180012b95  mov     r9d, ebx
0x180012b98  call    WPP_SF_d
0x180012b9d  jmp     short loc_180012BAD
0x180012b9f  mov     ebx, 57h ; 'W'
0x180012ba4  cmp     rcx, r15
0x180012ba7  jnz     loc_180012CA3
0x180012bad  lea     r11, [rsp+78h+var_18]
0x180012bb2  mov     eax, ebx
0x180012bb4  mov     rbp, [r11+28h]
0x180012bb8  mov     rsi, [r11+30h]
0x180012bbc  mov     rbx, [rsp+78h+arg_0]
0x180012bc4  mov     rsp, r11
0x180012bc7  pop     r15
0x180012bc9  pop     r14
0x180012bcb  pop     rdi
0x180012bcc  retn
0x180012bce  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bd5  cmp     rcx, r15
0x180012bd8  jnz     short loc_180012C3D
0x180012bda  mov     rax, [rdi]
0x180012bdd  cmp     [rax+8], rdi
0x180012be1  jnz     short loc_180012C0A
0x180012be3  mov     rcx, [rdi+8]
0x180012be7  cmp     [rcx], rdi
0x180012bea  jnz     short loc_180012C0A
0x180012bec  mov     [rcx], rax
0x180012bef  mov     [rax+8], rcx
0x180012bf3  lea     rcx, qword_1800AF038
0x180012bfa  mov     rax, cs:qword_1800AF040
0x180012c01  cmp     [rax], rcx
0x180012c04  jz      loc_180012D0C
0x180012c0a  mov     ecx, 3
0x180012c0f  int     29h; Win8: RtlFailFast(ecx)
0x180012c11  mov     rax, [rax]
0x180012c14  jmp     loc_180012AD6
0x180012c19  test    r14d, r14d
0x180012c1c  jz      loc_180012A80
0x180012c22  mov     ebx, 54Fh
0x180012c27  cmp     rcx, r15
0x180012c2a  jz      short loc_180012BAD
0x180012c2c  test    byte ptr [rcx+44h], 1
0x180012c30  jz      loc_180012B77
0x180012c36  mov     edx, 12h
0x180012c3b  jmp     short loc_180012CB2
0x180012c3d  test    byte ptr [rcx+44h], 2
0x180012c41  jz      short loc_180012BDA
0x180012c43  movzx   r9d, byte ptr [rdi+93Bh]
0x180012c4b  mov     edx, 14h
0x180012c50  movzx   eax, byte ptr [rdi+93Dh]
0x180012c57  movzx   r8d, byte ptr [rdi+93Ch]
0x180012c5f  movzx   r10d, byte ptr [rdi+93Ah]
0x180012c67  movzx   r11d, byte ptr [rdi+939h]
0x180012c6f  movzx   ebx, byte ptr [rdi+938h]
0x180012c76  mov     rcx, [rcx+38h]
0x180012c7a  mov     [rsp+78h+var_30], eax
0x180012c7e  mov     [rsp+78h+var_38], r8d
0x180012c83  mov     [rsp+78h+var_40], r9d
0x180012c88  mov     r9, rdi
0x180012c8b  mov     [rsp+78h+var_48], r10d
0x180012c90  mov     dword ptr [rsp+78h+var_50], r11d
0x180012c95  mov     dword ptr [rsp+78h+var_58], ebx
0x180012c99  call    WPP_SF_qDDDDDD
0x180012c9e  jmp     loc_180012BDA
0x180012ca3  test    byte ptr [rcx+44h], 1
0x180012ca7  jz      loc_180012B77
0x180012cad  mov     edx, 13h
0x180012cb2  mov     rcx, [rcx+38h]
0x180012cb6  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180012cbd  call    WPP_SF_
0x180012cc2  jmp     loc_180012B70
0x180012cc7  mov     rcx, [rcx+38h]
0x180012ccb  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180012cd2  mov     edx, 10h
0x180012cd7  call    WPP_SF_
0x180012cdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ce3  jmp     loc_180012A5E
0x180012ce8  mov     rcx, [rcx+38h]
0x180012cec  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180012cf3  mov     edx, 11h
0x180012cf8  mov     r9, rdi
0x180012cfb  call    WPP_SF_q
0x180012d00  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d07  jmp     loc_180012A70
0x180012d0c  mov     [rdi], rcx
0x180012d0f  mov     [rdi+8], rax
0x180012d13  mov     [rax], rdi
0x180012d16  mov     cs:qword_1800AF040, rdi
0x180012d1d  jmp     loc_180012B44
0x180012d22  mov     r9d, [rdi+9C0h]
0x180012d29  lea     rax, aRefing; ">>> Refing >>>"
0x180012d30  mov     rcx, [rbx+38h]
0x180012d34  mov     edx, 0Bh
0x180012d39  mov     [rsp+78h+var_58], rax
0x180012d3e  call    WPP_SF_Ls
0x180012d43  mov     rbx, cs:WPP_GLOBAL_Control
0x180012d4a  jmp     loc_180012B0A
0x180012d4f  movzx   ecx, byte ptr [rdi+93Ch]
0x180012d56  mov     edx, 0Ch
0x180012d5b  movzx   r8d, byte ptr [rdi+93Bh]
0x180012d63  movzx   r9d, byte ptr [rdi+93Ah]
0x180012d6b  movzx   eax, byte ptr [rdi+93Dh]
0x180012d72  movzx   r10d, byte ptr [rdi+939h]
0x180012d7a  movzx   r11d, byte ptr [rdi+938h]
0x180012d82  mov     [rsp+78h+var_20], eax
0x180012d86  mov     [rsp+78h+var_28], ecx
0x180012d8a  mov     rcx, [rbx+38h]
0x180012d8e  mov     [rsp+78h+var_30], r8d
0x180012d93  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180012d9a  mov     [rsp+78h+var_38], r9d
0x180012d9f  lea     r9, aSecmgrvalidate_1; "SecMgrValidateAndDeleteOrRefAdapter"
0x180012da6  mov     [rsp+78h+var_40], r10d
0x180012dab  mov     [rsp+78h+var_48], r11d
0x180012db0  mov     [rsp+78h+var_50], rdi
0x180012db5  mov     dword ptr [rsp+78h+var_58], 187h
0x180012dbd  call    WPP_SF_sdqDDDDDD
0x180012dc2  jmp     loc_180012B1C
0x180012dc7  mov     rcx, [rcx+38h]
0x180012dcb  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180012dd2  mov     edx, 0Dh
0x180012dd7  call    WPP_SF_d
0x180012ddc  jmp     loc_180012B44
```
