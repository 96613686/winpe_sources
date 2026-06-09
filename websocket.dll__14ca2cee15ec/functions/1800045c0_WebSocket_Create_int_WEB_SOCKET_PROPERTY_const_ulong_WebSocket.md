# WebSocket::Create(int,_WEB_SOCKET_PROPERTY * const,ulong,WebSocket * *)

- ea: `0x1800045c0`
- end: `0x180004828`
- name: `?Create@WebSocket@@SAJHQEAU_WEB_SOCKET_PROPERTY@@KPEAPEAV1@@Z`
- size: `616`
- prototype: `__int64 __fastcall(int, struct _WEB_SOCKET_PROPERTY *const, unsigned int, struct WebSocket **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800022b0`
- `0x1800022d0`

## callees

- `0x180001234`
- `0x180001274`
- `0x180001750`
- `0x180003cf8`
- `0x1800045c0`

## pseudocode

```c
__int64 __fastcall WebSocket::Create(
        int a1,
        struct _WEB_SOCKET_PROPERTY *const a2,
        unsigned int a3,
        struct WebSocket **a4)
{
  _QWORD *v4; // rsi
  _QWORD *v9; // rax
  _QWORD *v10; // rdi
  unsigned int v11; // ebx
  unsigned int *v12; // rax
  unsigned int *v13; // rdx
  int v14; // r10d
  unsigned int v15; // r9d
  int v16; // ecx
  int v17; // r11d
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  _QWORD *v21; // rax
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  _QWORD *v24; // rax

  v4 = &WebSocket::WebSocketDefaultClientProperties;
  if ( !a1 )
    v4 = &WebSocket::WebSocketDefaultServerProperties;
  v9 = operator new(0x28u);
  v10 = v9;
  if ( !v9 )
    return (unsigned int)-2147024882;
  v9[1] = 0;
  v9[2] = 0;
  v9[3] = 0;
  v9[4] = 0;
  *(_DWORD *)v9 = 1396852055;
  if ( !a2 && a3 || a3 > 0x1F )
  {
    v11 = -2147024809;
  }
  else
  {
    v12 = (unsigned int *)operator new(0x18u);
    v13 = v12;
    if ( v12 )
    {
      v14 = 0;
      v15 = 0;
      *(_OWORD *)v12 = *(_OWORD *)v4;
      *((_QWORD *)v12 + 2) = v4[2];
      if ( a3 )
      {
        while ( 1 )
        {
          v16 = *((_DWORD *)a2 + 6 * v15);
          v17 = 1 << v16;
          if ( ((1 << v16) & v14) != 0 )
            break;
          if ( v16 )
          {
            v18 = v16 - 1;
            if ( v18 )
            {
              v19 = v18 - 1;
              if ( v19 )
              {
                v20 = v19 - 1;
                if ( v20 )
                {
                  if ( v20 != 1 || *((_DWORD *)a2 + 6 * v15 + 4) != 4 )
                    break;
                  v13[3] = **((_DWORD **)a2 + 3 * v15 + 1);
                }
                else
                {
                  v21 = (_QWORD *)*((_QWORD *)a2 + 3 * v15 + 1);
                  if ( (*v21 & 7) != 0 )
                    break;
                  *((_QWORD *)v13 + 2) = *v21;
                }
              }
              else
              {
                if ( *((_DWORD *)a2 + 6 * v15 + 4) != 4 )
                  break;
                v13[2] = **((_DWORD **)a2 + 3 * v15 + 1);
              }
            }
            else
            {
              if ( *((_DWORD *)a2 + 6 * v15 + 4) != 4 )
                break;
              v22 = **((_DWORD **)a2 + 3 * v15 + 1);
              if ( v22 < 0x10 )
                break;
              v13[1] = v22;
            }
          }
          else
          {
            if ( *((_DWORD *)a2 + 6 * v15 + 4) != 4 )
              break;
            v23 = **((_DWORD **)a2 + 3 * v15 + 1);
            if ( v23 < 0x100 )
              break;
            *v13 = v23;
          }
          v14 |= v17;
          if ( ++v15 >= a3 )
            goto LABEL_29;
        }
        v11 = -2147024809;
        operator delete(v13);
        goto LABEL_41;
      }
LABEL_29:
      v10[4] = v13;
      if ( a1 )
      {
        *((_DWORD *)v10 + 1) = 0;
        v24 = operator new(0x70u);
        if ( v24 )
        {
          v24[3] = 0;
          v24[4] = 0;
          v24[5] = 0;
          v24[6] = 0;
          v24[7] = 0;
          v24[8] = 0;
          v24[9] = 0;
          v24[10] = 0;
          *v24 = 0;
          v24[12] = 0;
          v24[1] = 0;
          v24[2] = 0;
          v24[11] = 0;
        }
        else
        {
          v24 = 0;
        }
        v10[1] = v24;
      }
      else
      {
        *((_DWORD *)v10 + 1) = 3;
        v24 = operator new(0x70u);
        if ( v24 )
        {
          *v24 = 0;
          v24[1] = 0;
          v24[2] = 0;
          v24[3] = 0;
          v24[4] = 0;
          v24[5] = 0;
          v24[6] = 0;
          v24[7] = 0;
          v24[9] = 0;
          v24[10] = 0;
          v24[11] = 0;
          v24[12] = 0;
          v24[8] = 0;
        }
        else
        {
          v24 = 0;
        }
        v10[2] = v24;
      }
      if ( v24 )
      {
        v11 = 0;
        *a4 = (struct WebSocket *)v10;
        return v11;
      }
    }
    v11 = -2147024882;
  }
LABEL_41:
  WebSocket::~WebSocket((WebSocket *)v10);
  operator delete(v10);
  return v11;
}

```

## disassembly

```asm
0x1800045c0  push    rbx
0x1800045c2  push    rbp
0x1800045c3  push    rsi
0x1800045c4  push    rdi
0x1800045c5  push    r12
0x1800045c7  push    r14
0x1800045c9  push    r15
0x1800045cb  sub     rsp, 20h
0x1800045cf  xor     r12d, r12d
0x1800045d2  lea     rax, ?WebSocketDefaultServerProperties@WebSocket@@0UWebSocketProperties@@B; WebSocketProperties const WebSocket::WebSocketDefaultServerProperties
0x1800045d9  test    ecx, ecx
0x1800045db  lea     rsi, ?WebSocketDefaultClientProperties@WebSocket@@0UWebSocketProperties@@B; WebSocketProperties const WebSocket::WebSocketDefaultClientProperties
0x1800045e2  mov     r14d, ecx
0x1800045e5  mov     r15, r9
0x1800045e8  mov     ebp, r8d
0x1800045eb  mov     rbx, rdx
0x1800045ee  lea     ecx, [r12+28h]; Size
0x1800045f3  cmovz   rsi, rax
0x1800045f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800045fc  mov     rdi, rax
0x1800045ff  test    rax, rax
0x180004602  jz      loc_180004812
0x180004608  mov     [rax+8], r12
0x18000460c  mov     [rax+10h], r12
0x180004610  mov     [rax+18h], r12
0x180004614  mov     [rax+20h], r12
0x180004618  mov     dword ptr [rax], 53424557h
0x18000461e  test    rbx, rbx
0x180004621  jnz     short loc_180004631
0x180004623  test    ebp, ebp
0x180004625  jz      short loc_180004631
0x180004627  mov     ebx, 80070057h
0x18000462c  jmp     loc_1800047F3
0x180004631  cmp     ebp, 1Fh
0x180004634  ja      short loc_180004627
0x180004636  mov     ecx, 18h; Size
0x18000463b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004640  mov     rdx, rax
0x180004643  test    rax, rax
0x180004646  jz      loc_1800047EE
0x18000464c  mov     r10d, r12d
0x18000464f  mov     r9d, r12d
0x180004652  movups  xmm0, xmmword ptr [rsi]
0x180004655  movups  xmmword ptr [rax], xmm0
0x180004658  movsd   xmm1, qword ptr [rsi+10h]
0x18000465d  movsd   qword ptr [rax+10h], xmm1
0x180004662  test    ebp, ebp
0x180004664  jz      loc_18000472F
0x18000466a  mov     eax, r9d
0x18000466d  mov     r11d, 1
0x180004673  lea     r8, [rax+rax*2]
0x180004677  mov     ecx, [rbx+r8*8]
0x18000467b  shl     r11d, cl
0x18000467e  test    r10d, r11d
0x180004681  ja      loc_180004780
0x180004687  test    ecx, ecx
0x180004689  jz      short loc_180004707
0x18000468b  sub     ecx, 1
0x18000468e  jz      short loc_1800046EA
0x180004690  sub     ecx, 1
0x180004693  jz      short loc_1800046D2
0x180004695  sub     ecx, 1
0x180004698  jz      short loc_1800046BB
0x18000469a  cmp     ecx, 1
0x18000469d  jnz     loc_180004780
0x1800046a3  cmp     dword ptr [rbx+r8*8+10h], 4
0x1800046a9  jnz     loc_180004780
0x1800046af  mov     rax, [rbx+r8*8+8]
0x1800046b4  mov     ecx, [rax]
0x1800046b6  mov     [rdx+0Ch], ecx
0x1800046b9  jmp     short loc_180004720
0x1800046bb  mov     rax, [rbx+r8*8+8]
0x1800046c0  mov     rcx, [rax]
0x1800046c3  test    cl, 7
0x1800046c6  ja      loc_180004780
0x1800046cc  mov     [rdx+10h], rcx
0x1800046d0  jmp     short loc_180004720
0x1800046d2  cmp     dword ptr [rbx+r8*8+10h], 4
0x1800046d8  jnz     loc_180004780
0x1800046de  mov     rax, [rbx+r8*8+8]
0x1800046e3  mov     ecx, [rax]
0x1800046e5  mov     [rdx+8], ecx
0x1800046e8  jmp     short loc_180004720
0x1800046ea  cmp     dword ptr [rbx+r8*8+10h], 4
0x1800046f0  jnz     loc_180004780
0x1800046f6  mov     rax, [rbx+r8*8+8]
0x1800046fb  mov     ecx, [rax]
0x1800046fd  cmp     ecx, 10h
0x180004700  jb      short loc_180004780
0x180004702  mov     [rdx+4], ecx
0x180004705  jmp     short loc_180004720
0x180004707  cmp     dword ptr [rbx+r8*8+10h], 4
0x18000470d  jnz     short loc_180004780
0x18000470f  mov     rax, [rbx+r8*8+8]
0x180004714  mov     ecx, [rax]
0x180004716  cmp     ecx, 100h
0x18000471c  jb      short loc_180004780
0x18000471e  mov     [rdx], ecx
0x180004720  or      r10d, r11d
0x180004723  inc     r9d
0x180004726  cmp     r9d, ebp
0x180004729  jb      loc_18000466A
0x18000472f  mov     [rdi+20h], rdx
0x180004733  mov     ecx, 70h ; 'p'; Size
0x180004738  test    r14d, r14d
0x18000473b  jz      short loc_18000479C
0x18000473d  mov     [rdi+4], r12d
0x180004741  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004746  test    rax, rax
0x180004749  jz      short loc_180004793
0x18000474b  mov     [rax+18h], r12
0x18000474f  mov     [rax+20h], r12
0x180004753  mov     [rax+28h], r12
0x180004757  mov     [rax+30h], r12
0x18000475b  mov     [rax+38h], r12
0x18000475f  mov     [rax+40h], r12
0x180004763  mov     [rax+48h], r12
0x180004767  mov     [rax+50h], r12
0x18000476b  mov     [rax], r12
0x18000476e  mov     [rax+60h], r12
0x180004772  mov     [rax+8], r12
0x180004776  mov     [rax+10h], r12
0x18000477a  mov     [rax+58h], r12
0x18000477e  jmp     short loc_180004796
0x180004780  mov     rcx, rdx; Block
0x180004783  mov     ebx, 80070057h
0x180004788  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000478d  test    ebx, ebx
0x18000478f  jns     short loc_180004733
0x180004791  jmp     short loc_1800047F3
0x180004793  mov     rax, r12
0x180004796  mov     [rdi+8], rax
0x18000479a  jmp     short loc_1800047E9
0x18000479c  mov     dword ptr [rdi+4], 3
0x1800047a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800047a8  test    rax, rax
0x1800047ab  jz      short loc_1800047E2
0x1800047ad  mov     [rax], r12
0x1800047b0  mov     [rax+8], r12
0x1800047b4  mov     [rax+10h], r12
0x1800047b8  mov     [rax+18h], r12
0x1800047bc  mov     [rax+20h], r12
0x1800047c0  mov     [rax+28h], r12
0x1800047c4  mov     [rax+30h], r12
0x1800047c8  mov     [rax+38h], r12
0x1800047cc  mov     [rax+48h], r12
0x1800047d0  mov     [rax+50h], r12
0x1800047d4  mov     [rax+58h], r12
0x1800047d8  mov     [rax+60h], r12
0x1800047dc  mov     [rax+40h], r12
0x1800047e0  jmp     short loc_1800047E5
0x1800047e2  mov     rax, r12
0x1800047e5  mov     [rdi+10h], rax
0x1800047e9  test    rax, rax
0x1800047ec  jnz     short loc_18000480A
0x1800047ee  mov     ebx, 8007000Eh
0x1800047f3  mov     rcx, rdi; this
0x1800047f6  call    ??1WebSocket@@QEAA@XZ; WebSocket::~WebSocket(void)
0x1800047fb  mov     edx, 28h ; '('
0x180004800  mov     rcx, rdi; Block
0x180004803  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004808  jmp     short loc_180004817
0x18000480a  mov     ebx, r12d
0x18000480d  mov     [r15], rdi
0x180004810  jmp     short loc_180004817
0x180004812  mov     ebx, 8007000Eh
0x180004817  mov     eax, ebx
0x180004819  add     rsp, 20h
0x18000481d  pop     r15
0x18000481f  pop     r14
0x180004821  pop     r12
0x180004823  pop     rdi
0x180004824  pop     rsi
0x180004825  pop     rbp
0x180004826  pop     rbx
0x180004827  retn
```
